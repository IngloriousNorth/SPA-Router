# WELCOME to TEMPLAR-SPA-ROUTER!

On a simple initialization with a config object, TEMPLAR automatically routes your HTML partials, and includes functions for getting #anchor_page_url, Query Params, manual routing, and, miraculously, a helm() config option that automatically runs a function (which can contain Architecture-Agnostic app functions at the programmer's leisure) on every page load. With this you get a Router that is Application-Agonistic, so you don't need to learn a huge constraining library like ANGULAR or REACT.

# DOCUMENTATION
## OVERVIEW
### Manual-Route
```
  TEMPLAR.route("#partial_name");
  TEMPLAR.route("#table?sales=1);
```

### GET PAGE
```
  if(TEMPLAR.pageREC() === "partialName") //no # before partial_name
    partialNameFn();
```

Best Practice: Run functions automatically on client Route using the helm[] config property.

### Return URL-QUERY-PARAMS
```
  TEMPLAR.paramREC().index

  //OR
  const params = TEMPLAR paramREC();
  var i = params.index
```
### Set URL-QUERY-PARAMS
```
  TEMPLAR.paramSET({
    id: "123",
    tab: "settings",
    filter: "active"
});
//I don't really use this, I just route and include the params in the #route?param=
```

## INITIALIZATION
TEMPLAR is an Architecture-Agnostic Router, but before you start your personal SPA app, run 
```
TEMPLAR.initialize(config, ()=>{
  onAppStart(); //(optional)
})
```
If you do not want to start your app from TEMPLAR, simply synchronously run 
```
  TEMPLAR.initialize(config);
```
Before you start your app functions.

## DIR STRUCTURE

Put your partials.html in a client/partials folder, or set the partial dir in your config object.

### EXAMPLE
client/partials/home.html //this partial shows when TEMPLAR.pageREC() is "home"<br>
client/partials/table.html //this partial shows when TEMPLAR.pageREC() is "table"<br><br>
Make sure your directory structure has the partials.html with the partial (shared with ANCHOR#URL) name, corresponding to the HTML structure.

## HTML STRUCTURE
```
<body>
  <header></header><!-- optional, TEMPLAR-agnostic !-->
  <div class="TEMPLAR home"></div>
  <div class="TEMPLAR table"></div>
  <footer></footer><!--optional, TEMPLAR-agnostic !-->
</body>
```
## CONFIG
```
  const config = {
        defaultPage: "home",
        dir: "client/partials",
        fade: false,
        pages: ["home", "table"]
  }
  //before you start your leisurely app fns()
  TEMPLAR.initialize(config);
```

## AUTO-ROUTE:
-add "TEMPLAR" as First-Class of your &lt;div&gt; SPA partial
-add "TEMPLAR as First-Class of your &lt;a&gt;.
-add "partial_name" to second class of &lt;div&gt; and &lt;a&gt; (-- this is also your #URL name)
### Example:
```
  <div class="menu">
    <a class="TEMPLAR home>Home</a>
    <a class="TEMPLAR home>table</a>
  </div>
  <div class="TEMPLAR home">Home</div>
  <div class="TEMPLAR table">Table</div>

```

## MANUAL-ROUTE
```
  TEMPLAR.route("#home") //routes to <div class="TEMPLAR home"
  TEMPLAR.route("#table?id=1");
```
## HELM AUTO-Fns() ON ROUTE!
Where helm is a config property ie 
```
const config = {
  pages :["home", "table"],
  helm : helm
}:
const helm = [
            {
                page: "table",
                fn: function() {
                   initializeTable(TEMPLAR.paramREC().id);
                }
            }
]
```
Helm is optional, and even if you have a helm, if your page has no JS (like "home"), you needn't include it! 

## MAINFRAME-MVC MODULE
This is completely optional, but this is how TEMPLAR works with the MAINFRAME-MVC plugin:
```
  const helm = [
              {
                  page: "table",
                  fn: function() {
                     MVC.Controller.Table.initialize(TEMPLAR.paramREC().id);
                  }
              }
  ]
```
This way you organize your code MVC, in a modular way, with TEMPLAR and MAINFRAME.
