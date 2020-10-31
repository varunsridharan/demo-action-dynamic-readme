> File includes only work if its starts & end with a html comment 
>
> to avoid rendering Usage Block we have used `\!`. make sure to use only `!` to render the file include.

```
<\!-- include file.md --> 
```

---

## Local File With Relative Path
Include a file from the current file's location 

### Usage :

<pre>
<\!-- include ./parts/license.md -->
</pre>

<details> 
<summary>Output :</summary>

<pre>
<!-- include ./parts/license.md -->
</pre>

</details>

---
## Local File With Absolute Path
Include a file located inside this repository

### Usage :

<pre>
<\!-- include templates/file-includes/parts/feedback.md -->
</pre>

<details> 
<summary>Output :</summary>

<pre>
<!-- include templates/file-includes/parts/feedback.md -->
</pre>

</details>

---
## Include File Inside Codeblock
dynamic-template.yml github action yaml file which in in this repository will be included below

### Usage :

<pre>
<\!-- include [code:yml] .github/workflows/dynamic-template.yml -->
</pre>

<details> 
<summary>Output :</summary>

<pre>
<!-- include [code:yml] .github/workflows/dynamic-template.yml -->
</pre>

</details>

---
## Including File From A Remote Repository
You can include any type of file from any repository. if you want to include from a **Private** Repository then you have to provide **Github Personal Access Token** Instead **Github Token** in action's workflow file

### Usage :

```
Include from remote repository
<\!-- include {owner}/{repo}/{filepath}/{file} -->


Include from remote repository with specific branch
<\!-- include {owner}/{name}@{branch}/{filepath}/{file} -->
```
> **Note** : use `@` when loading files from specific branch
>
> Example : [`octocat/Spoon-Knife@master/README.md`](https://github.com/octocat/Spoon-Knife) file will be loaded below.
>
> Using : `<\!-- include octocat/Spoon-Knife@master/README.md -->`

<details> 
<summary>Output :</summary>

<pre>
<!-- include octocat/Spoon-Knife@master/README.md -->
</pre>

</details>

---
## Including File From Global Repository Template
You can also configure a global template repository in action's workflow like `GLOBAL_TEMPLATE_REPOSITORY` and actions takes care of loading files from it. when using global template option you dont need to provide configure repository details in the include comment instead just load file like `<\!-- include file.md -->`

### Usage :

```<\!-- include sponsor.md -->```

> If `sponsor.md` not found it current repository then it will check for the same in Global Template Repository & if found it will be loaded.

<details> 
<summary>Output :</summary>

<pre>
<!-- include sponsor.md -->
</pre>

</details>

---
