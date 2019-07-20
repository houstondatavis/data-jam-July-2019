# data-jam-July-2019

#### In this data jam, we will visualize the Federal Government's Open-Source code!

The General Services Administration (GSA) is responsible for code.gov, a site that aggregates open-source code projects from across government agencies. Code.gov <a href="https://www.code.gov/about/compliance/inventory-code">establishes</a> metadata standards for code.json to follow and where they should go in order to be automatically harvested for inclusion in code.gov. Each federal agency should be storing their code.json in a page like data.<agency name>.gov/code.json. For example, the NSA's is https://code.nsa.gov/code.json 

Exporting all the repositories gets you metadata on more than 6,000 code projects.

## Getting the Data

### The Code.gov API
Code.gov has relatively recently started providing an API, which is described <a href="https://developers.code.gov/basics.html"> here</a>.

You have to request an API key to use the API, but it is a quick proces to get one.

The API is documented via SWAGGER on <a href="https://api.code.gov/docs/#/repo/get_repos">this website</a>, which you can submit dummy queries via a GUI. 

If you have a little bit of experience working with APIs or would like to start, working directly with the API is one way to go.

There are some examples below in JavaScript and Python, which call the API that might serve as a starting point.

### Static Datasets Created Using the Code.gov API
You have two options for working with static files that are pre-exported  (exported July 14th, 2019) for you from the API. There is a 

The flattened_all_repos_US_code_July15.csv and all_repos_with_nesting.json files were exported on July 14th using <a href="https://observablehq.com/@justingosses/code-gov-demo-dataset-retrieval">this</a> Observable Notebook that calls the API.
https://observablehq.com/@justingosses/code-gov-demo-dataset-retrieval

The API returns JSON. I have combined multiple JSON returned into a single big JSON as the API limits you to <1000 results each call. 

The JSON results are also nested, so I've also flattened them into a CSV. 

<b>Due to dealing with the nesting, the fields are not identical between the JSON and the CSV.</b>.

#### The CSV is there if your preferred data visualization tool simply can't handle JSON and you don't want to mess with the API. However, the CSV conversion isn't perfect, so the JSON will most likely be the easiest to work with. 

If you use Tableau for example, definitely use the JSON. Same with Python, JavaScript, R, etc.

<b>The JSON</b> that is exported from the API is included in this repository. It is called = all_repos_with_nesting.json. It is organized by code repository should have 5000+ entries. You should be able to click on the download button <a href="https://github.com/houstondatavis/data-jam-July-2019/blob/master/all_repos_with_nesting.json"> on this page</a> and it will download.

## The Challenge
On the code.gov <a href="https://www.code.gov/browse-projects?page=1&size=10&sort=data_quality">browse page</a> you'll see that there is a nice search interface on the page. This a great user interface if you already know what you're looking for or have a good idea what might be useful to you that exists, but what if you aren't entering the page with a strong idea what could be there that would be interest to you? The current page is a little weak in terms of discoverability, which data visualization might help with.

To be clear, these aren't needs code.gov has asked the public for, but they do everything out in the public and, I'm guessing based on comments in their github repositories, would likely appreciate the feedback. 

You can also submit change requests for their metadata scheme, website, or API on their many github repositories. They are also reachable on a 18F slack channel that is mentioned in some repositories. 

#### Some prompts to optionally pick from:
- Who published the most open-source code?
- Who publishes similiar code?
- What can we say about how code projects have been added over time?
- What aggregated views would help people understand what is there? 
- Could a data visualization be added to the webpage to make it more discoverable for curious new users what is there?
- What data is suspect or bad quality?
- How does the data supplied differ across agencies & organizations?
- What data visualization can you make to help yourself find useful code for you?
- What percentage of projects on code.gov are open-source vs. government-source? How do government-only projects differ?


## Related Resources

### Examples:
Licenses of NASA open-source code projects
https://observablehq.com/@justingosses/licenses-of-open-source-nasa-code-projects-on-code-gov

Use the API to create a JSON or CSV
https://observablehq.com/@justingosses/code-gov-demo-dataset-retrieval

Download a CSV of licenses in projects on code.gov
https://observablehq.com/@danieljdufour/csv-of-licenses-of-projects-on-code-gov

Observable Data Visualization Notebooks that Use the Code.gov API are linked to from their website using search results for code.gov on Observable url:
Some of these: https://observablehq.com/search?query=%22code.gov%22

Quick Tableau Public Notebook Using the JSON in this repository to enable filtered results by Orgs, Tags, and Language: https://public.tableau.com/profile/justin.gosses#!/vizhome/Code_govAPIquicklookv1July2019ForHoustonDataVisMeetup/FilterProjectbyAgencyTagsLanguage?publish=yes

Github Repository with links to code tied to code.gov
https://github.com/GSA/code-gov
The link above is a repository that links to all other code.gov related repositories. A lot of the code for their websites and API is all public on github.com.

#### There are also some example Jupyter notebooks that are work looking at as a starting point:
 
<a href="https://github.com/GSA/code-gov-stats">Code.gov Stats</a>

<a href="https://github.com/GSA/code-gov-stats-jupyter-notebook"> Code.gov notebooks for demoing what can be done with the API</a> There is one here that is used for getting out github stats like forks and stars that has been useful. An exported CSV file from that notebook enabled creation of <a href="https://observablehq.com/@justingosses/public-engagement-with-nasas-open-source-code-projects-on-g">this</a> Observable data visualization of popular NASA code repositories. 
