TEMPLAR automatically routes your HTML pages, when you use class "TEMLAR" on a partial and an [a] element that you want to link-route to the second class, what represents the partial_name, of [a, div].

Before you start your app, run TEMPLAR.initialize(config, function(){
}), where the second parameter is an (optional) callback function.

Put your partials.html in a client/partials folder, or set the dir in your const config object.



```
TEMPLAR.initialize(config, ()=>{
  onAppStart(); //(optional)
})
```

TEMPLAR.initialize takes a {helm: []} object. The functions in the helm run on every Route of your page. 

### HTML STRUCTURE
```
<body>
  <header></header><!-- optional, TEMPLAR-agnostic !-->
  <div class="TEMPLAR home"></div>
  <div class="TEMPLAR about_us"></div>
  <footer></footer><!--optional, TEMPLAR-agnostic !-->
</body>
```

### AUTO-ROUTE:
-add "TEMPLAR" to your <div> partial and

TEMPEST.route("#partial") //routes to <div class="TEMPEST partial"
