# TAXISnet — скилл Claude для налоговой декларации на Кипре

[English version](README.md)

Скилл для Claude, который через браузер проводит по подаче декларации о доходах физлица
(**TD1 / EPR1**) за прошлый налоговый год в [TAXISnet](https://taxisnet.mof.gov.cy)
и останавливается на расчёте налога — проверяет и подаёт декларацию **сам пользователь**.

## Что делает

1. Открывает TAXISnet и просит **вас самостоятельно войти** в окне браузера.
2. Проверяет список деклараций: есть ли подача за прошлый налоговый год.
3. Если есть черновик — открывает его; если нет — создаёт (после вашего подтверждения);
   если уже подана — останавливается.
4. Вносит данные из ваших справок **Т.Φ. 63 (IR63)** — от одного или нескольких
   работодателей — после вашего подтверждения (автоматической загрузки IR63 в TAXISnet нет).
5. Уточняет у вас прочие доходы и вычеты, сверяет их с правилами налогового года
   (срок, лимит вычетов 1/5, вычеты, которые действуют только с 2026), показывает,
   что будет введено, и заполняет форму после вашего «да».
6. Нажимает **SELF-ASSESSMENT / CONTRIBUTIONS**, показывает итог расчёта и проверяет его
   по шкале налога и ставкам SDC / GHS.
7. Передаёт управление вам: вы проверяете все данные и сами подаёте декларацию.

## Чего не делает никогда

- Не запрашивает, не принимает и не вводит логин, пароль и одноразовые коды.
- Не нажимает финальную кнопку **Submit** / **Υποβολή**.
- Не проводит платежи и не удаляет черновики и документы.
- Не выдумывает суммы и не даёт налоговых консультаций.

## Требования

- Claude с доступом к браузеру: встроенный браузер в приложении Claude для компьютера
  или Claude in Chrome.
- Учётная запись TAXISnet (физическое лицо).
- Справка Т.Φ. 63 (IR63) от каждого работодателя и документы по прочим доходам
  и вычетам.

## Установка

### Claude Code (плагин)

```
/plugin marketplace add ittermit/taxisnet
/plugin install taxisnet@taxisnet
```

### Приложение Claude (claude.ai / desktop)

1. Скачайте папку [`skills/cyprus-tax-declaration`](skills/cyprus-tax-declaration)
   (или весь репозиторий архивом и извлеките эту папку).
2. Упакуйте папку `cyprus-tax-declaration` в ZIP.
3. Загрузите ZIP в разделе навыков (skills) в настройках Claude.

## Использование

Напишите Claude, например:

> Подготовь мою налоговую декларацию на Кипре за прошлый год в TAXISnet.

Claude откроет браузер, попросит вас войти и пойдёт по шагам выше.

## Структура репозитория

```
.claude-plugin/
  plugin.json          # манифест плагина
  marketplace.json     # установка из этого репозитория в Claude Code
skills/
  cyprus-tax-declaration/
    SKILL.md           # инструкции скилла
    references/
      official-guide-2025.md # официальное руководство 2025, по разделам формы
      rules-2025.md    # правила за 2025: срок, ставки, вычеты, SDC/GHS
      taxisnet-notes.md # как устроен TAXISnet: статусы, предзаполнение, IR63, оплата
      checklist.md     # что Claude спросит у вас
README.md / README.ru.md
CHANGELOG.md
LICENSE
```

## Известные ограничения

- Встроенные налоговые правила относятся только к **2025 налоговому году** (подача в 2026
  через TAXISnet). С 2026 налогового года декларации подаются в Tax For All — это скилл
  не покрывает.
- Шаги заполнения соответствуют официальному руководству за 2025 год, но ещё не
  прогонялись на живой форме TAXISnet; названия могут немного отличаться.
- TAXISnet может разлогинить при бездействии — Claude попросит войти снова.

## Отказ от ответственности

Проект не связан с Налоговым департаментом Кипра или Министерством финансов.
Это не налоговая консультация. Ответственность за проверку данных и подачу декларации
лежит на вас. Если сомневаетесь, что нужно декларировать, обратитесь к налоговому
консультанту.

## Источники

Правила и заметки в `skills/cyprus-tax-declaration/references/` собраны 14 октября 2026
года. Основной источник — официальные материалы Налогового департамента; остальные
источники использованы для контекста и перекрёстной проверки.

Официальные (Налоговый департамент Кипра / TAXISnet):
- [Руководство по заполнению декларации физлица за 2025 год (PDF, на греческом)](https://www.gov.cy/media/sites/167/2026/06/Guide-for-completion-of-tax-return-2025-EL.pdf)
- [Страница Налогового департамента о декларации физлица](https://www.gov.cy/mof-tax/documents/forologiki-dilosi-eisodimatos-atomoy/)
- [Объявление о начале подачи деклараций за 2025 (18 июня 2026)](https://www.gov.cy/oikonomia/anakoinosi-tou-tmimatos-forologias-anaforika-me-tin-enarxi-tis-ypovolis-tis-dilosis-eisodimatos-atomou-gia-to-forologiko-etos-2025/)
- [Что учесть — частые ошибки](https://www.gov.cy/mof-tax/documents/forologiki-dilosi-eisodimatos-atomoy/ti-prepei-na-prosexete-sychna-lathi/)
- [Удалённая работа на работодателя за пределами Кипра](https://www.gov.cy/mof-tax/documents/forologiki-dilosi-eisodimatos-atomoy/ex-apostaseos-ergasia-se-ergodoti-ektos-tis-dimokratias-i-kai-parochi-ypiresion-ektos-tis-dimokratias/)
- [TAXISnet FAQ — электронная подача деклараций](https://taxisnet.mof.gov.cy/displayFaq.do?dispatch=faq5Ird)
- Справочные документы TAXISnet о временном сохранении и финальной подаче, лимите
  времени на форму и возврате декларации во временный статус (инструкции по Intrastat /
  НДС из информационных материалов TAXISnet)

Срок, обязанность подачи, штрафы и сезон 2025 в TAXISnet:
- [C. Markou & Co — декларация за 2025 до 31 октября 2026](https://www.cmarkou.com/2025-personal-income-tax-return-due-by-31-october-2026/)
- [Politis — TAXISnet открыт для деклараций за 2025, штраф за просрочку повышен](https://en.politis.com.cy/news/economy/1012362/taxisnet-opens-for-2025-returns-as-cyprus-raises-late-filing-fines)
- [Sigmalive — подача через TAXISnet до 31 октября](https://en.sigmalive.com/?p=68186)
- [RegFollower — продление срока подачи за 2025](https://regfollower.com/cyprus-extends-2025-personal-income-tax-filing-deadline/)
- [Globalserve — продление срока для деклараций физлиц за 2025](https://www.gstaxconsultants.com/deadline-extension-for-2025-individual-income-tax-returns/)
- [Andersen Cyprus — подача деклараций за 2025](https://cy.andersen.com/news/cyprus-news-submission-of-2025-income-tax-returns/)
- [SPL — обновление Налогового департамента по T.D.1](https://splcy.com/tax-alert-update-on-personal-income-tax-return-y2025/)
- [PwC Cyprus — TD1 за 2024: продление до 15 октября 2025](https://www.pwc.com.cy/en/publications/direct-tax-updates-2025/dtu-n14-2025.pdf)

Налоговые правила (ставки, вычеты, льготы, SDC, GHS, резидентство):
- [PwC Tax Summaries — Кипр: налоги на доходы физлиц](https://taxsummaries.pwc.com/Cyprus/Individual/Taxes-on-personal-income)
- [PwC Tax Summaries — Кипр: вычеты](https://taxsummaries.pwc.com/cyprus/individual/deductions)
- [TaxApp — 5 частых ошибок при подаче за 2025](https://taxapp.cy/5-common-mistakes-to-avoid-for-the-2025-tax-filing-in-cyprus/)
- [Rightax — льготы для первого трудоустройства (20% / 50%)](https://rightax.com.cy/https-rightax-com-cy-cyprus-tax-incentives-highly-paid-first-employment/)
- [Mondaq — налогообложение пассивного дохода на Кипре](https://www.mondaq.com/passive-income-taxation-in-cyprus-%E2%80%93-an-update/1755734)
- [KPMG Cyprus — налоговое резидентство и non-dom](https://assets.kpmg.com/content/dam/kpmg/cy/pdf/2024/cyprus-tax-residency-and-non-dom-rules.pdf)

Работа с TAXISnet и практические советы:
- [Abasis — TAXISnet или Tax For All: какой портал для 2025 и 2026](https://cyprustaxcalculator.abasis.ai/guides/which-portal/)
- [Cyprus Tax Life — руководство по TAXISnet](https://www.cyprustaxlife.com/blog/cyprus-tax-portal-taxisnet)
- [CyExpat — как подать декларацию на Кипре](https://www.cyexpat.com/en/articles/posts/file-taxes-cyprus/)
- [CyEasy — налоговые формы (TD1, IR63, TD59)](https://cyeasy.tax/en/forms)

Во вторичных источниках бывают ошибки; где они расходились, в скилле использованы
данные, подтверждённые несколькими источниками.

## Лицензия

[MIT](LICENSE)
