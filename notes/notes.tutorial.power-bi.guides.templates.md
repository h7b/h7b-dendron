---
id: k5iutwqa761epx8w0f8kloc
title: Report templates in Power BI
desc: Use report templates in Power BI Desktop
updated: 1661679933433
created: 1661678662098
---
# Use report templates in Power BI Desktop

ref: [microsoft](https://docs.microsoft.com/en-us/power-bi/create-reports/desktop-templates)

## Create report templates

Power BI report templates contain the following information from the report from which they were generated:
- Report pages, visuals, and other visual elements
- The data model definition, including the schema, relationships, measures, and other model definition items
- All query definitions, such as queries, Query Parameters, and other query elements

What is not included in templates is the report's data.

Report templates use the file extension `.PBIT` (compare to Power BI Desktop reports, which use the `.PBIX` extension).

Power BI report template files are generally much smaller than a Power BI Desktop report, because templates to not contain any data - just the report definitions themselves.

![export-powerbi-template](https://cdn-aldpb.nitrocdn.com/MmRYricBGnwFelNvIykEOHWwZuUwjnwj/assets/static/optimized/rev-f109493/wp-content/uploads/2019/11/export-power-bi-template-button.png){max-width: 300px, display: block, margin: 0 auto}

## Use report templates

You can open Power BI report templates in two ways:
- Double-click on any `.PBIT` file to automatically launch Power BI Desktop and load the template
- Select File > Import > Power BI template from within Power BI Desktop

![import-powerbi-template](https://docs.microsoft.com/en-us/power-bi/create-reports/media/desktop-templates/desktop-templates-04.png){max-width: 300px, display: block, margin: 0 auto}

The template's user does not have access to the report's source data. That is why templates are often used with [query parameters](https://docs.microsoft.com/en-us/power-query/power-query-query-parameters). When you open a report template, a dialog may appear. The dialog asks for values for any parameters that are defined in the report the template is based on.

![query-parameters](https://docs.microsoft.com/en-us/power-query/images/me-parameters-manage-parameters.png){max-width: 300px, display: block, margin: 0 auto}

## Related

- [How to Power BI](https://www.youtube.com/shorts/J0kGO6AhCqE)
- [spreadsheeto | How to Use Templates in Power BI](https://spreadsheeto.com/power-bi-templates/)