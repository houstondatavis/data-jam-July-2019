# data-jam-July-2019
dataset for july 2019 data jam on a dataset of open-source projects from federal government agencies

The General Services Administration (GSA) is responsible for code.gov, a site that aggregates open-source code projects from across government agencies. Code.gov <a href="https://www.code.gov/about/compliance/inventory-code">establishes</a> metadata standards for code.json to follow and where they should go in order to be automatically harvested for inclusion in code.gov. Each federal agency should be storing their code.json in a page like data.<agency name>.gov/code.json. For example, data.nasa.gov/code.json. 

## The Code.gov API
Code.gov has relatively recently started providing an API, which is described <a href="https://developers.code.gov/basics.html"> here</a>.

You have to request an API key to use the API, but it is a quick proces to get one.

Swagger docs can be found here: https://api.code.gov/docs/

## Related Resources
### Observable Data Visualization Notebooks that Use the Code.gov API are linked to from their website!

https://observablehq.com/search?query=%22code.gov%22

### Github Repository of Useful & Related Code
https://github.com/GSA/code-gov

The link above is a repository that links to all other code.gov related repositories. A lot of the code for their websites and API is all public on github.com.

### There are also some example Jupyter notebooks that are work looking at:
 
<a href="https://github.com/GSA/code-gov-stats">Code.gov Stats</a>

<a href="https://github.com/GSA/code-gov-stats-jupyter-notebook"> Code.gov notebooks for demoing what can be done with the API</a> There is one here that is used for getting out github stats like forks and stars that has been useful. An exported CSV file from that notebook enabled creation of <a href="https://observablehq.com/@justingosses/public-engagement-with-nasas-open-source-code-projects-on-g">this</a> Observable data visualization of popular NASA code repositories. 

## The Data
1. Option 1: Use the code.gov API mentioned above.
2. Option 2: Use exported static files generated from the API. These files were generated using the API in this Observable notebook <a href="https://observablehq.com/@justingosses/code-gov-demo-dataset-retrieval">here</a>. The API returns JSON. I have combined multiple JSON returned into a single big JSON as the API limits you to <1000 results each call. The JSON results are nested, so I've also flattened them into a CSV. Due to dealing with the nesting, the fields are not identical between the JSON and the CSV.

The CSV that is exported from the API that will be included in this repository. It is called = flattened_all_repos_US_code.csv. It is organized by code repository should have 5000+ entries. You should be able to click on the<a href="https://github.com/houstondatavis/data-jam-July-2019/blob/master/flattened_all_repos_US_code.csv">download button on this page</a> and it will download. Note that the the CSV is flattened and some information may be lost of complicated in comparison to the JSON, but the CSV is fine to work with if you're not very comfortable working with nested JSON in the time you have.

The JSON that is exported from the API that will be included in this repository. It is called = all_repos_with_nesting.json. It is organized by code repository should have 5000+ entries. You should be able to click on the<a href="https://github.com/houstondatavis/data-jam-July-2019/blob/master/all_repos_with_nesting.json">download button on this page</a> and it will download.

## The Challenge
On the code.gov <a href="https://www.code.gov/browse-projects?page=1&size=10&sort=data_quality">browse page</a> you'll see that there is a nice search interface on the page. This a great user interface if you already know what you're looking for or have a good idea what might be useful to you that exists, but what if you aren't entering the page with a strong idea what could be there that would be interest to you? The current page is a little weak in this area. 
- It doesn't present any aggregated views except maybe for languages used, agencies, and licenses. 
- Could a data visualization be added to the webpage to make it more discoverable for curious new users what is there?
- What parts of the metadata of the code projects could be used, aggregated, cross-linked, filtered, or displayed?
- How could user's experiences, skills, interests be used?

To be clear, these aren't needs code.gov has asked the public for, but they do everything out in the public and, I'm guessing based on comments in their github repositories, would likely appreciate the feedback. 

### Examples:
Licenses of NASA open-source code projects
https://observablehq.com/@justingosses/licenses-of-open-source-nasa-code-projects-on-code-gov

https://observablehq.com/@justingosses/code-gov-demo-dataset-retrieval
