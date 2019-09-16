### Features

- Create pages easily
- Fire customized function with page selection
- Customize class help for more flexibility
- Minified version 4.4kb

### Links

`<demo page>` : <https://okisht.github.io/Jquery-Paginator/paginator>

Before start: All the function in paginator.js you should call with referance page

For ex you will call initPaginator func, then it will be like paginator.initPaginator(yourData);

or if you gonna call destroy ; paginator.destroyPaginator();


### HTML

Add below html before init paginator

```html
  <div class="col-md-12 paginator js-paginator">

  </div>
```

### Javascript

Call 'initpaginator' function to create your pages

__'previousPage'__ :  for naming previous page button (string) - Default is Previous Page

__'nextPage'__:  for naming next page button (string) - Default is Next Page

__'totalPage'__:  total pages number (int)

__'triggerFunc'__:  the function name that you want to fire after pages created

__'paginationClass'__:  customize your class for the parent element (string)


```javascript
 $(document).ready(function () {
    paginator.initPaginator({
      'previousPage': 'Next Page',
      'nextPage': 'Previous Page',
      'totalPage': 34,
      'triggerFunc': test,
      'paginationClass': 'paginatorCustomClass'
    });
  });
```
The function example which is triggered right after pages created

```javascript
  function test() {
    var selectdPg = $('.js-paginator').data('pageSelected');
    $('.js-test').text('page ' + selectdPg);
  }
```

__Destroy__ paginator
```javascript
    paginator.destroyPaginator();
```

#### Total page changes
for changing the total number of the page dynamically
you can call the function 'paginatorPages'.
Before you call this function, you should know there are 3 parameters;

__pageTotal__: new total page number(int)

__changedClass__: new customized class if you want to change something with css or etc (string) - if you dont send this parameter your first customized class will not change.

__selectedPage__: if you want to specify your selected page with init this function (int). default page is 1.


So your function will be like : 
__paginator.paginatorPages(pageTotal, 'newCustClass', paginationClass);__

Special thanks to [@sseymakaya](https://github.com/sseymakaya) for testing.


### End
