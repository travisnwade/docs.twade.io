# Help for MKDocs

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

For more reading, checkout Squidfunk's docs on this usage here: [squidfuck.github.io](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#usage)        