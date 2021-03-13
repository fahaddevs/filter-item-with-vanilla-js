## Filter items with vanilla JS
---

[Demo link](https://fahaddevs.github.io/filter-item-with-vanilla-js/)

First you have to create a array for all your items and store them each single object.
```js
const products = [
  {
    id: 1, 
    title: 'Bread and coffee', 
    category: 'breakfast',
    price: 15.99,
    img: './images/1.jpg',
    desc: 'Dolor sit amet consectetur adipisicing elit. Aperiam placeat ipsum voluptates voluptatum modi deleniti reiciendis odio corrupti rem sunt hic quas sed architecto ea, impedit fugit. Quae, eaque nihil.'
  },
  {
    id: 2, 
    title: 'Oats, Staberry, Yogurt', 
    category: 'breakfast',
    price: 25.99,
    img: './images/2.jpg',
    desc: 'Dolor sit amet consectetur adipisicing elit. Aperiam placeat ipsum voluptates voluptatum modi deleniti reiciendis odio corrupti rem sunt hic quas sed architecto ea, impedit fugit. Quae, eaque nihil.'
  },
  {
    id: 3, 
    title: 'Yogurt, Staberry', 
    category: 'breakfast',
    price: 12.99,
    img: './images/3.jpg',
    desc: 'Dolor sit amet consectetur adipisicing elit. Aperiam placeat ipsum voluptates voluptatum modi deleniti reiciendis odio corrupti rem sunt hic quas sed architecto ea, impedit fugit. Quae, eaque nihil.'
  },
  {
    id: 4, 
    title: 'Burger', 
    category: 'lunch',
    price: 35.99,
    img: './images/4.jpg',
    desc: 'Dolor sit amet consectetur adipisicing elit. Aperiam placeat ipsum voluptates voluptatum modi deleniti reiciendis odio corrupti rem sunt hic quas sed architecto ea, impedit fugit. Quae, eaque nihil.'
  },
  {
    id: 5, 
    title: 'Shorma', 
    category: 'lunch',
    price: 15.99,
    img: './images/5.jpg',
    desc: 'Dolor sit amet consectetur adipisicing elit. Aperiam placeat ipsum voluptates voluptatum modi deleniti reiciendis odio corrupti rem sunt hic quas sed architecto ea, impedit fugit. Quae, eaque nihil.'
  },
  {
    id: 6, 
    title: 'Tanduri chiken', 
    category: 'breakfast',
    price: 65.99,
    img: './images/6.jpg',
    desc: 'Dolor sit amet consectetur adipisicing elit. Aperiam placeat ipsum voluptates voluptatum modi deleniti reiciendis odio corrupti rem sunt hic quas sed architecto ea, impedit fugit. Quae, eaque nihil.'
  },
  {
    id: 7, 
    title: 'Cheiken Carry', 
    category: 'lunch',
    price: 55.99,
    img: './images/7.jpg',
    desc: 'Dolor sit amet consectetur adipisicing elit. Aperiam placeat ipsum voluptates voluptatum modi deleniti reiciendis odio corrupti rem sunt hic quas sed architecto ea, impedit fugit. Quae, eaque nihil.'
  },
  {
    id: 8, 
    title: 'Coconut Shake', 
    category: 'shake',
    price: 8.99,
    img: './images/8.jpg',
    desc: 'Dolor sit amet consectetur adipisicing elit. Aperiam placeat ipsum voluptates voluptatum modi deleniti reiciendis odio corrupti rem sunt hic quas sed architecto ea, impedit fugit. Quae, eaque nihil.'
  },
  {
    id: 9, 
    title: 'Chocolate Shake', 
    category: 'shake',
    price: 13.99,
    img: './images/9.jpg',
    desc: 'Dolor sit amet consectetur adipisicing elit. Aperiam placeat ipsum voluptates voluptatum modi deleniti reiciendis odio corrupti rem sunt hic quas sed architecto ea, impedit fugit. Quae, eaque nihil.'
  },
  {
    id: 10, 
    title: 'Straberry Shake', 
    category: 'shake',
    price: 22.99,
    img: './images/10.jpg',
    desc: 'Dolor sit amet consectetur adipisicing elit. Aperiam placeat ipsum voluptates voluptatum modi deleniti reiciendis odio corrupti rem sunt hic quas sed architecto ea, impedit fugit. Quae, eaque nihil.'
  }
]
```

Select products container and filter buttons
```js 
// all items container
const wrapper = document.querySelector('.product-wrapper');
// filter btn
const btns = document.querySelectorAll('.filter-btn');
``` 

And then create a function for getting all dynamic content from the `products array` 
```js 
// funtion for getting all dynamic content from array use map method.
function displayItems (displayItem){
  let displayProducts = displayItem.map(function(product){
    return `<div class="col-lg-6">
              <div class="product rounded-3 border p-3 shadow">
                <div class="thumb">
                  <img src=${product.img} alt=${product.title}>
                </div>
                <div class="content">
                  <h3 class="title">${product.title}</h3>
                  <h4 class="price">$${product.price}</h4>
                  <p class="product-details">${product.desc}</p>
                </div>
              </div>
            </div>`;
  });
  displayProducts = displayProducts.join("");
  wrapper.innerHTML = displayProducts;
}
```

Then show all items when DOM is loaded
```js 
// show all items when DOM is loaded
window.addEventListener('DOMContentLoaded', function(){
  displayItems(products);
});
```

Then create a loop for filter button and get specific items from the `products array` 
```js
// filter items when specific button is clicked
btns.forEach(function(btn){
  btn.addEventListener('click', function(e){
    const category = e.currentTarget.dataset.id;
    const menuCategory = products.filter(function(productItem){
      if (productItem.category == category){
        return productItem
      }
    });
    // console.log(menuCategory);
    if (category == 'all'){
      displayItems(products)
    } else {
      displayItems(menuCategory);
    }
  });
});
```

[Demo link](https://fahaddevs.github.io/filter-item-with-vanilla-js/)

##### If you're interested this project, Please contribute and hit the star button.

| Social Medias | Links                                                      |
| ------------- | ---------------------------------------------------------- |
| Facebook      | [Facebook Profile](https://www.facebook.com/fahaddevs)     |
| Linkedin      | [Linkedin Profile](https://www.linkedin.com/in/fahaddevs/) |
| Twitter       | [Twitter Profile](https://twitter.com/fahaddevs)           |
| Instagram     | [Instagram Profile](https://www.instagram.com/fahaddevs/)  |
| CodePen       | [CodePen Profile](https://codepen.io/fahaddevs/)           |
| Youtube       | [CodePen Profile](https://youtube.com/fahaddevs/)           |