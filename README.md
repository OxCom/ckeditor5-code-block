# Ckeditor5: CodeBlock & PrismJS
[CKEditor5](https://ckeditor.com/ckeditor-5/) code block feature for integration with [PrismJS](https://prismjs.com)

**NOTE:** Only for [custom builds](https://ckeditor.com/docs/ckeditor5/latest/builds/guides/development/custom-builds.html).

## Install
1) Create folders ```/src/plugun/codeblock```
2) Put the content ```src``` folder from current repo to ```/src/plugun/codeblock``` of you ckeditor build 
3) In your ```ckeditor.js``` update configuration:
    ```javascript
    // ...
    import CodeBlock from './plugin/codeblock/codeblock';
    // ...
    ClassicEditor.builtinPlugins = [
       // ...
       // TableToolbar,
       // ... add plugin to build in list
       CodeBlock
    ];
    // ... 
    ClassicEditor.defaultConfig = {
       // ... provide default configuration
       codeblock: {
           languages: [ 'cpp', 'cs', 'lua', 'xml', 'js', 'php' ]
       },
       // ... add new button for toolbar
       toolbar: {
            items: [
               // ...
               // 'mediaEmbed',
               'codeblock',
               // ...
            ]
       },
       // ...
    };
    ```

In a result you should have code-block feature that will render next structure:
```html
<pre class="line-numbers"><code class="lang-cpp">#include &lt;codeblock>
using everywhere;
</code></pre>
```

**NOTE**: In editor code block will be not highlighted. You have apply PrismJS in your applications 
where you render results from editor (news page, blog post, etc.).

## TODO
- Write tests
- Create documentations
- Cleanup the code
