> File includes only work if its starts & end with a html comment 
>
> to avoid rendering Usage Block we have used `\!`. make sure to use only `!` to render the file include.

Inline Includes & Reusable includes dose the same work. but this can come in handy when you are generating template & saving it in the same file
it preserves include comment and will be parsed again when Re-generating the template & contents of that include will be updated

```
<\!-- START file.md --> 
<\!-- END file.md --> 
```

---

{{ CONTENT }}
