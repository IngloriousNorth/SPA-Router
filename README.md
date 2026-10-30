TEMPLAR automatically routes your HTML pages, when you use class "TEMLAR" on a partial and an [a] element that you want to link-route to the second class, what represents the partial_name, of [a, div].

# DOCUMENTATION

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
-add "TEMPLAR" as First-Class of your &lt;div&rt; SPA partial
-add "TEMPLAR as First-Class of your &lt;a&rt;.
-add "partial_name" to second class of &lt;div&rt; and &lt;a&lt; (-- this is also your #URL name)
### Example:
```
  <div class="menu">
    <a class="TEMPLAR home>Home</a>
    <a class="TEMPLAR home>table</a>
  </div>
  <div class="TEMPLAR home">Home</div>
  <div class="TEMPLAR table">Table</div>

```

TEMPEST.route("#partial") //routes to <div class="TEMPEST partial"
