TEMPLAR automatically routes your HTML pages, when you use class "TEMLAR" on a partial and an [a] element that you want to link-route to the second class, what represents the partial_name, of [a, div].

Put your partials.html in a client/partials folder, or set the dir in TEMPLAR.initialize().

```
TEMPLAR.initialize(config, ()=>{
  onAppStart(); //(optional)
})
```

TEMPLAR.initialize takes a {helm: []} object. The functions in the helm run on every Route of your page. 

OR MANUALLY ROUTE:

TEMPEST.route("#partial") //routes to <div class="TEMPEST partial"
