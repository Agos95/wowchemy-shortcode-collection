# Better Table

Improved version of the `table` shortcode, to allow a deeper configuration and an easier way to target specific class with custom css. The new parameters assign additional bootstrap classes besides the default `table`. 
See [Bootstrap Tables documentation](https://getbootstrap.com/docs/4.6/content/tables/) for more information about the classes.

In order to be non-breaking with the base `table` shortcut, the default values of the parameters lead to the same output of the base shortcut.

## Add the shortcode to your site

Install your shortcode in your site by referencing it at the bottom of your `config/_default/config.yaml`:

```yaml
module:
  imports:
    # your existing imports
    - path: githib.com/Agos95/wowchemy-shortcode-collection/shortcodes/better-table
```

## Parameters

- **`src` : *str***  
    Path or url to the csv table. Path is relative to the folder where the shortcode is called.

- **`delimiter` : *str, default ","***  
    Cell delimiter.

- **`header` : bool, default true**  
    If true, first row is interpreted as the header.

- **`caption` : *str, default ""***  
    Caption for the table.

- **`striped` : *bool, default false***  
    If true, add the class `table-striped`, to make alternate rows of different colors.

- **`hover` : *bool, default false***  
    If true, add the class `table-hover`, to enable a hover state on the current row.  
    *[**NOTE**: when styling with css, "color" attribute work, while "background-color" does not]*

- **`responsive` : *bool or str, default false***  
    If true, it defaults to "md".
    If a str must be one of ["sm", "md", "lg", "xl"], otherwise it defaults to "md".
    If not false, add the class `table-responsive-$responsive`,
    to make the table horizontable scrollable under the specified breakpoint.

- **`small` : *bool, default false***  
    If true, add the class "table-sm", to make the table more compact by cutting cell padding in half.

- **`halign` : *str, default ""***  
    Horizontal text alignment for the table.
    If passed, must be one of ["left", "center", "right"], otherwise it defaults to "left".

## Additional Changes

- Header row is encapsulated inside <thead> tag