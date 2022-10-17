

# Securing your repositories supply chain

<!--step0

GitHub helps you secure your supply chain, from understanding the dependencies in your environment, to knowing about vulnerabilities in those dependencies, and patching them.

- **Who is this for**: Developers, DevOps engineers, SREs, Security experts, managers, teams.
- **What you'll learn**: How to view repository dependecies, view Dependabot alelrts, enable Dependabot security and version updates.
- **What you'll build**: Dependecies, Dependabot alerts, pull requests to fix dependecies and version updates.
- **Prerequisites**: You create your repository as a public repository.
- **How long**: This course is 4 steps long and can be completed in under an hour.

<summary><h2> How to start this course!</h2></summary>
 
1. Above these instructions, right-click **Use this template** and open the link in a new tab.
   ![Use this template](https://user-images.githubusercontent.com/1221423/169618716-fb17528d-f332-4fc5-a11a-eaa23562665e.png)
2. In the new tab, follow the prompts to create a new repository.
   - For owner, choose your personal account or an organization to host the repository.
   - We recommend creating a public repository—private repositories will [use Actions minutes](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions).
   ![Create a new repository](https://user-images.githubusercontent.com/1221423/169618722-406dc508-add4-4074-83f0-c7a7ad87f6f3.png)
3. After your new repository is created, wait about 20 seconds, then refresh the page. Follow the step-by-step instructions in the new repository's README.

endstep0-->

<details id=1>
<summary><h2>Step 1: Review and add dependecies using Dependency graph</h2></summary>

_Welcome to "Securing your repositories supply chain"! :wave:_

**What is Securing your repositories supply chain**: GitHub helps you secure your supply chain, from understanding the dependencies in your environment, to knowing about vulnerabilities in those dependencies, and patching them.

* To read more about Secuirng your repositories supply chain: [Secuirng your repositories supply chain](https://docs.github.com/en/code-security/supply-chain-security/understanding-your-software-supply-chain/about-supply-chain-security)
   
**What is a Dependency Graph**: The dependency graph is a summary of the manifest and lock files stored in a repository and any dependencies that are submitted for the repository using the Dependency submission API (beta). For each repository, it shows:

* Dependencies, the ecosystems and packages it depends on
* Dependents, the repositories and packages that depend on it
* To ready more about Dependency graph: [Dependency graph](https://docs.github.com/en/code-security/supply-chain-security/understanding-your-software-supply-chain/about-the-dependency-graph)

### :keyboard: Activity: Verify Dependency graph enabled

1. Open a new browser tab, and work on the steps in your second tab while you read the instructions in this tab.
2. Navigate to the `Settings` tab.
3. Click on `Code security and analysis`.   
4. Verify/enable Dependency graph. If the repo is private you will enable it here. If the repo is public it will be enabled by default.
5. Move on to the next activity.

### :keyboard: Activity: View dependencies

1. Navigate to the `Insights` tab.
2. Click on `Dependency` graph.
3. Review all the dependecies on the `Dependencies` hub.
4. Learn how to explore dependencies: [Explore dependecies](https://docs.github.com/en/code-security/supply-chain-security/understanding-your-software-supply-chain/exploring-the-dependencies-of-a-repository)
5. Move on to the next activity.

### :keyboard: Activity: Add and view dependency

1. Navigate to the `Code` tab.
2. Navigate to the `code/src/AttendeeSite` folder
3. Add the following content to the `package-lock.json` file after the third to last `}`
   ```
   ,
    "follow-redirects": {
      "version": "1.14.1",
      "resolved": "https://registry.npmjs.org/follow-redirects/-/follow-redirects-1.14.1.tgz",
      "integrity": "sha512-HWqDgT7ZEkqRzBvc2s64vSZ/hfOceEol3ac/7tKwzuvEyWx3/4UegXh5oBOIotkGsObyk3xznnSRVADBgWSQVg=="
    }
   ```
4. Navigate to the `Insights` tab.
5. Click on `Dependency` graph.
6. Review all new dependecies on the `Dependencies` hub.
7. Search for `follow-redirects` and review the dependancy.
8. Wait about 20 seconds then refresh this page for the next step.

</details>

<details id=2 open>
<summary><h2>Step 2: Enable and view Dependabot alerts</h2></summary>

_Nice work! :tada: You added and viewed a dependency with `Dependency graph`!_

Next, we need to enable and view dependabot alerts.

**What are Dependabot alerts**: Dependabot alerts tell you that your code depends on a package that is insecure. Dependabot alerts references The GitHub Advisory Database that contains a list of known security vulnerabilities and malware, grouped in two categories: GitHub-reviewed advisories and unreviewed advisories.

* About Dependabot alerts: [Dependabot alerts](https://docs.github.com/en/code-security/dependabot/dependabot-alerts/about-dependabot-alerts)
* About GitHub Advisory Database: [GitHub Advisory Database](https://docs.github.com/en/code-security/dependabot/dependabot-alerts/browsing-security-advisories-in-the-github-advisory-database)
 
### :keyboard: Activity: View security advisories in the GitHub Advisory Database

1. Open a new browser tab.
2. Navigate to the [GitHub Advisory Database](https://github.com/advisories).
3. Type or paste `follow-redirects` into the search box.
4. Click on any of the advisories that were found.
5. Note the packages, impact, patches, workaround and referennces for the advisory.
6. Move on to the next activity.

 ### :keyboard: Activity: Enable Dependabot alerts

1. Open a new browser tab, and work on the steps in your second tab while you read the instructions in this tab.
2. Navigate to the `Settings` tab.
3. Click on `Code security and analysis`.  
4. Click `Enable` Dependabot alerts.
5. Wait about 60 seconds then click on the `Security` tab at the top of the repository.
6. Verify there are 4 `Dependabot` alerts under the `Vulnerability alerts` section.
7. Revew each alert.
8. Move on to the next activity.
 
 ### :keyboard: Activity: Create a Pull Request based on a Dependabot alert

1. Click on `Prototype Pollution in minimist` alert under the `Dependabot alerts` section.
2. View the alert.
3. Click `Create Dependabot security update` button. The will create a pull request for the fix.
4. Wait until the pull request is created. This could take ~2 minutes.
5. Click on `Review security update` button. The pull request will be displayed.
6. View the pull request. View the `Files changed` tab to review the update.
7. Navigate back to the `Conversation` tab.
8. Click on `Merge pull request` button.
9. Click `confirm merge` button.
10. Wait about 20 seconds then refresh this page for the next step.
 
</details>

<details id=3>
<summary><h2>Step 3: Enable and trigger Dependabot security updates</h2></summary>

_Nice work enabling, viewing and creating Dependabot alerts :sparkles:_

**What is Dependabot security updates**: Dependabot can fix vulnerable dependencies for you by raising pull requests with security updates.
 
 * To learn more about Dependabot security updates: [Dependabot security updates](https://docs.github.com/en/code-security/dependabot/dependabot-security-updates/about-dependabot-security-updates)

### :keyboard: Activity: Enable and trigger Dependabot security updates

1. Open a new browser tab, and work on the steps in your second tab while you read the instructions in this tab.
2. Navigate to the `Settings` tab.
3. Click on `Code security and analysis`.  
4. Click Enable on `Dependabot security updates`.
5. Wait until a pull request shows up under the `Pull requests` repository tab. Shoud be about 60 seconds then click on the `Pull requests` tab at the top of the repository.
6. Verify there is a new pull request titled `Bump axios from 0.21.1 to 0.21.2 in /code/src/AttendeeSite`.
7. View the pull request.
8. Click on `Merge pull request` button.
9. Click `confirm merge` button.
10. Wait about 20 seconds then refresh this page for the next step.

</details>

<details id=4>
<summary><h2>Step 4: Enable and trigger Dependabot version updates</h2></summary>

_Nicely done Enable and trigger Dependabot security updates! :partying_face:_

**What is enable and trigger Dependabot version updates**: You can use Dependabot to keep the packages you use updated to the latest versions.

* To learn more about Dependabot version updates: [Dependabot version updates](https://docs.github.com/en/code-security/dependabot/dependabot-version-updates/about-dependabot-version-updates)

### :keyboard: Activity: Enable and trigger Dependabot version updates

1. Open a new browser tab, and work on the steps in your second tab while you read the instructions in this tab.
2. Navigate to the `Settings` tab.
3. Click on `Code security and analysis`.  
4. Click Enable on `Dependabot version updates`.
5. A new file editor opens with pre polulated contents. The file is called `dependabot.yml`.
6. Add `nuget` to the `package-ecosystem`.
7. Change the `directory` to `/code/`.
8. The `dependabot.yml` file should look like this:
![Screen Shot 2022-09-27 at 6 52 45 AM](https://user-images.githubusercontent.com/26442605/192545528-dfc33648-94ce-4421-8710-c5bb0a41b0ec.png)
9. Click `Commit changes` directly to the main branch.
10. Wait about 20 seconds then refresh this page for the next step.


</details>

<details id=X>
<summary><h2>Finish</h2></summary>

_Congratulations friend, you've completed this course!_

<img src=TBD-celebrate-image alt=celebrate width=300 align=right>

Here's a recap of all the tasks you've accomplished in your repository:

* You've leearned how to view and use Dependency graph.
* You've learned how to enable and use Dependabot alerts.
* You've learned how to ennable and use Dependabot secuirty updates.
* You've learned how to ennable and use Dependabot version updates.

### What's next?

- Learn more about securing your supply chain by reading: [Securing your supply chain](https://docs.github.com/en/code-security/supply-chain-security/understanding-your-software-supply-chain/about-supply-chain-security).
- [We'd love to hear what you thought of this course](https://github.com/skills/.github/discussions).
- [Take another TBD-organization Course](https://github.com/TBD-organization](https://github.com/skills).
- [Read the GitHub Getting Started docs](https://docs.github.com/en/get-started).
- To find projects to contribute to, check out [GitHub Explore](https://github.com/explore).

</details>

<!--
  <<< Author notes: Footer >>>
  Add a link to get support, GitHub status page, code of conduct, license link.
-->

---

Get help: [TBD-support](TBD-support-link) &bull; [Review the GitHub status page](https://www.githubstatus.com/)

&copy; 2022 TBD-copyright-holder &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [CC-BY-4.0 License](https://creativecommons.org/licenses/by/4.0/legalcode)
