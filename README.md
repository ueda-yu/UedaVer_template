# Synopsys GitHub Templates

Modern applications are a complex mix of proprietary and open source code, APIs and user interfaces, application behavior, and deployment workflows. Security issues at any point in this software supply chain can leave you and your customers  at risk. Synopsys solutions help you identify and   manage software supply chain risks end-to-end.

The Synopsys GitHub DevOps Templates repository contains a collection of .yml templates, and composite GitHub Actions that can be used to integrate Synopsys AST solutions into your GitHub CI/CD workflows.
For the workflow templates, it is recommended that you clone this repo into a copy within your own organization, and then leverage these workflows according to GitHub best practices:

- [Sharing workflows, secrets, and runners with your organization](https://docs.github.com/en/actions/learn-github-actions/sharing-workflows-secrets-and-runners-with-your-organization).
- [Using workflow templates](https://docs.github.com/en/actions/learn-github-actions/using-workflow-templates)

For the composite GitHub Actions, these are provided as reference examples that you can use as-is or copy and modify to suit your own purposes. 

These templates and scripts are provided under an OSS license (specified in the LICENSE file) and have been developed by Synopsys field engineers as a contribution to the Synopsys user community. Please direct questions and comments to the appropriate forum in the Synopsys user community.

# Available Templates

## Coverity

Run a Coverity SAST scan as part of your GitHub CI/CD workflow. These templates are written for the traditional cov-build or cov-capture workflow, with cov-analyze or cov-run-desktop running locally and a central Coverity Connect server. There are two instances of this recipe:

- [coverity](coverity/README.md) - For traditional Coverity, using Coverity Connect and cov-build/cov-capture/cov-analyze. This is a composite GitHub action that contains only workflow steps as configuration as code. 
This recipe implements the current recommended best practices for running Coverity in a GitHub workflow and the README can provide more details.
- [coverity-simple](coverity-simple.yml) - Simple example of how you might add the cov-report-output-v7-json to an existing GitHub Workflow.
- [coverity-thin-client](coverity-thin-client/README.md) - Coming soon! A composite GitHub action that demonstrates how to use the Coverity CLI and new Coverity Scan Service to offload analysis jobs from your GitHub runners.

The templates use the [Coverity Report Output V7 JSON Action](https://github.com/synopsys-sig/coverity-report-output-v7-json) to provide feedback to developers. Please see the action's own README for details on how it works.

## Polaris

Run a Polaris SAST scan as part of your GitHub CI/CD workflow. These templates are written for the
SaaS version of Coverity running on Polaris.

- [polaris](https://github.com/jcroall/polaris-report-action) - For Polaris running on SaaS using the Polaris CLI. This recipe includes developer
feedback on pull requests and has the potential for future enhancements like security gates and SARIF support.

## Black Duck

Run a Black Duck SCA scan as part of your GitHub CI/CD workflow. The two templates include:

- [blackduck.yml](blackduck.yml) - Runs Black Duck Rapid Scan on pull requests (this may run multiple times, as changes are added to the pull request) and a Full/Intelligent scan on pushes to main branches. For pull requests, feedback
is limited to only new policy violations introduced by the change. For pushes, the full Black Duck scan is run including signature and binary analysis and no feedback is provided within GitHub. 
- [blackduck-intelligent-scheduled.yml](blackduck-intelligent-scheduled.yml) - Runs Black Duck Full (or "Intelligent") Scan on a schedule. If running a full/intelligent scan on every push is too much for your environment (in the above
template there will be at least one rapid and one intelligent for every PR - one when the PR is created, and the other when the PR is merged and a push is received) you may prefer to run the intelligent scans on a schedule. This provides
an example of how to run them on a cron style schedule managed by GitHub.

The templates use the [Black Duck Detect Action](https://github.com/synopsys-sig/detect-action) to provide feedback to developers. Please see the action's own README    for details on how it works.

Each template is commented fully to explain each step of the process.

The Black Duck detect process is very lightweight, and these can be used easily on both GitHub-hosted and Self-hosted runners.

# Future Enhancements

Future templates will include:

- Coverity CLI support, including the new Thin Client and Scan Service
- Polaris support
"# Ueda_synopsys-github-templates" 
"# UedaVer_template" 
