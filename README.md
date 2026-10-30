TEMPLAR automatically routes your HTML pages, when you use class "TEMLAR" on a partial and an [a] element that you want to link-route to the second class, what represents the partial_name, of [a, div].

# DOCUMENTATION

## INITIALIZATION
Before you start your app, run TEMPLAR.initialize(config, function(){
}), where the second parameter is an (optional) callback function.

```
TEMPLAR.initialize(config, ()=>{
  onAppStart(); //(optional)
})
```
## DIR STRUCTURE

Put your partials.html in a client/partials folder, or set the partial directory in your config object.

client/partials/home.html //this page shows when URL is #home
client/partials/table.html //this partial shows when URL is #table

## HTML STRUCTURE
```
<body>
  <header></header><!-- optional, TEMPLAR-agnostic !-->
  <div class="TEMPLAR home"></div>
  <div class="TEMPLAR table"></div>
  <footer></footer><!--optional, TEMPLAR-agnostic !-->
</body>
```

## AUTO-ROUTE:
-add "TEMPLAR" as first-class of your &lt;div&rt; SPA partial
-add "TEMPLAR as first-class of your &lt;a&rt; that routes to &lt;div&rt;TEMPLAR.second-class -- this is your #ANCHOR page title!
-second class of [a] and [div]
```
  <div class="TEMPLAR table_page"


TEMPEST.route("#partial") //routes to <div class="TEMPEST partial"
