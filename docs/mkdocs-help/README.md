# Help for MKDocs

## Official MKDocs Wiki

The offical page for MKDocs can be found here: [https://www.mkdocs.org/](https://www.mkdocs.org/)

## mkdocs.yml Example

This is an example of my current `mkdocs.yml` file for this site:

``` { .yml }
site_name: Travis Wade Wiki
site_url: https://docs.twade.io
site_description: A flat-file, stupid simple docs and wiki platform hosted on Netlify and maintained by Travis Wade.
site_author: Travis Wade
copyright: © 2023 <a href="https://links.twade.io" target="_blank">Travis Wade</a>
extra_css:
- css/custom.css
extra_javascript:
- js/custom.js  
theme: readthedocs
markdown_extensions:
- footnotes
- pymdownx.critic  
- pymdownx.superfences 
- pymdownx.details  
- attr_list
- def_list
- fenced_code
- meta
- admonition  
nav:
- Docs:
    - Home: index.md
    - Netlify: netlify/index.md
    - Windows: windows/index.md
    - Powershell: powershell/index.md
    - Ansible: ansible/index.md
    - MKDocs Help: mkdocs-help/index.md    
    - About: about.md
- Tools:
    - 'Online Markdown Editor': https://markdown.twade.io/" target="_blank
    - 'Markdown Reference Sheet': https://markdown.twade.io/markdown-reference/" target="_blank
    - Downloads: downloads/index.md
- Awesome Extras:
    - 'Awesome Self Hosted': https://github.com/awesome-selfhosted/awesome-selfhosted#table-of-contents" target="_blank
- More About Travis:
    - 'Github': https://github.com/travisnwade" target="_blank
    - 'LinkedIn': https://www.linkedin.com/in/traviswade/" target="_blank
    - 'Instagram': https://www.instagram.com/tn_wade/" target="_blank
    - 'Links Page': https://links.twade.io  " target="_blank   
```

## Opening Links in New Tab

### Automatically open external links in a new tab

This one requires you to create a new folder and new `.js` file. As well as a slight modification to your `mkdocs.yml` file.

First, the new `.js` file.  You can name it whatever you like, I just named mine `custom.js`.

Place the following line of code as the content of your new `.js` file that will handle this action:

``` { .javascript }
!function(){for(var e=document.body.getElementsByTagName("a"),t=e.length,n=0;n<t;n++)new URL(e[n].href).origin!==location.origin&&e[n].setAttribute("target","_blank")}();
```

I placed this in a new folder under the `docs` directory.  Like such:

    docs
    -- js
        -- custom.js

And in my `mkdocs.yml` file:

    extra_javascript:
    - js/custom.js 

### Opening Nav link in new tab

You can reference my `mkdocs.yml` file above for how I achieve this, but here is some sample code to show how I'm doing it:

    nav:
    - MENU ITEM:
        - 'Name of the Menu item': https://links.twade.io " target="_blank

Stripped down version of my nav on this site that shows how I added my `github` profile in the nav so it opens in a new window:

    nav:
    - More About Travis:
        - 'Github': https://github.com/travisnwade" target="_blank

## Footnotes

This is an example of a footnote[^1] 

[^1]: 
    This is the description of the footnote itself. 
    Which should render at the bottom of the page. 
    For more reading, read here: [python-markdown-extension-footnotes](https://python-markdown.github.io/extensions/footnotes/)

Here's how the footnote is written in Markdown:

``` { .markdown }
This is an example of a footnote[^1] 

[^1]: 
    This is the description of the footnote itself. 
    Which should render at the bottom of the page. 
    For more reading, read here: [python-markdown-extension-footnotes](https://python-markdown.github.io/extensions/footnotes/)
```

## Buttons

### Primary Buttons

[Subscribe to our newsletter](#){ .md-button .md-button--primary }

This is achieved via:

    [Subscribe to our newsletter](#){ .md-button .md-button--primary }


### Normal Buttons

[Subscribe to our newsletter](#){ .md-button }

This is achieved via:

    [Subscribe to our newsletter](#){ .md-button }


### Button Styling

Here is the styling achieved with the buttons on this site:

    .md-button {
        padding: 15px;
        margin: 6px 8px 6px 8px;
        min-width: 88px;
        border-radius: 8px;
        font-size: 16px;
        text-align: center;
        text-transform: uppercase;
        text-decoration: none;
        border: none;
        outline: none;
        background-color: #404040;
        color: #fff;
    }

    .md-button--primary {
        padding: 12px;
        margin: 6px 8px 6px 8px;
        min-width: 88px;
        border-radius: 8px;
        font-size: 16px;
        text-align: center;
        text-transform: uppercase;
        text-decoration: none;
        border: none;
        outline: none;
        background-color: #606a69;
        color: #fff
    }  


## Admonitions

These are basically ways to highlight or _callout_ certain bodies of text for importance.

For example:

!!! note "This is the title of the note"
    This is the content of the note.
    The "meat" of what you want to amplify
    within the note.

This is achieved via:    

    !!! note "This is the title of the note"
        This is the content of the note.
        The "meat" of what you want to amplify
        within the note.

!!! note ""
    You can also remove the title if it's not needed.

Which can be done via:
    
    !!! note ""
        You can also remove the title if it's not needed.     

### Supported types

!!! note "Note"
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

!!! abstract "Abstract"    
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

!!! info "Info"
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

!!! tip "Tip"
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

!!! success "Success"
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

!!! question "Question"    
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

!!! warning "Warning"    
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

!!! failure "Failure"    
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

!!! danger "Danger"    
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

!!! bug "Bug"    
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

!!! example "Example"    
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

!!! quote "Quote"    
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.


### Further reading on Admonitions

For more reading, checkout Squidfunk's docs on this usage here: [squidfunk.github.io](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#usage)        

## Fenced Code

This is especially handy when you want the correct syntax when highlighting code.

### HTML

``` { .html }
<a href="#">A link</a>
<p>Should render as html code here.</p>
```    

    ``` { .html }
    <a href="#">A link</a>
    <p>Should render as html code here.</p>
    ```  

### PowerShell

``` { .powershell }
Get-CimInstance -ClassName Win32_OperatingSystem | Invoke-CimMethod -MethodName Shutdown
```

    ``` { .powershell }
    Get-CimInstance -ClassName Win32_OperatingSystem | Invoke-CimMethod -MethodName Shutdown
    ```

## Building

    mkdocs build