# WebDevelopmentPractice

## JS_pratice

1. CountDown  
   1-1. !+ tab => generate html page  
   1-2. reload a new page : location.href = 'https://www.google.com';

2. verification code  
   2-1. Math.round(Math.random() \* (updound - lowbound) + lowbound);  
   2-2.  
   //<input id="btn" type="button" value="NAME_ON_BUTTON" />  
   //<input id="inputedCode" type="text" />  
   2-3. import css file
   //<link href="./index.css" rel="stylesheet" type="text/css" />  
   2-4. [for in lable] connects to [other element's id ]  
   once you click on text area that label is wrapping,  
   the same operation to click on the [ element ] with connected id  
   <label for="inputedCode">Input Verfication Code:</label>

   2-5. form controls (input, button, select, and textarea)[.value]  
    any other element[.innerText];

   You only use value on form controls (input, button, select, and textarea). For any other element, if you want its text, use textContent or innerText (or, depending on your use case, innerHTML).

   The only tricky one there is button, which is the only form control that has both a value and text.  
   The value of a button is the value that will be submitted if that button submits the form it's in. The text is what the user sees as the button caption. Here's an example:  
   // const btn = document.querySelector("button");  
   // console.log(`The button's value is: ${btn.value}`);//42  
   // console.log(`The button's textContent is: ${btn.textContent}`);//Forty-Two  
   // <button value="42">Forty-Two</button>

   2-6.  
   The return value of an event handler determines whether or not the default browser behaviour should take place as well.  
   In the case of clicking on links, this would be following the link,  
   but the difference is most noticeable in form submit handlers,  
   where you can cancel a form submission if the user has made a mistake entering the information.

   return false is actually doing three very separate things when you call it:  
    event.preventDefault();  
    event.stopPropagation();  
    Stops callback execution and returns immediately when called.

3. card-flip && spite animation
4. search bar in real time  
   4-1. <p> is a block element ，<input> is a inline element.  
   (star)4-2. (div) show.innerHTML="<p>"+ item+"</p>"(+"<p>"+ item+"</p>"+"<p>"+ item+"</p>")  
   4-3. if(null)=> false;  
   4-4. String.indexOf(searchValue [, fromIndex]),if there is no matched value,return -1;  
   4-5. xxxxx.style.display="xxxx";  
   4-6. xxxx.onblur

5. lottery  
   5-1. if (timer == null) , and timer = setInterval(() => offset the impact of opening many setInterval.  
   5-2.  
   width: 33%;  
   height: 33%;  
   3 rows，3 collum

6. toDOList
   6-1. `<li> ${elt.text} </li>`;  
   6-2.  
    const text = this.querySelector('[name=item]').value;  
   <input type="text" name="item" placeholder="Item Name" required />

   const checkboxs = document.querySelectorAll('input[type=checkbox]');  
   <input type="checkbox"  id="item${index}"/>

   6-3. event.preventDefault();
   6-4.  
    this.reset();  
    //the same as this.querySelector('[name=item]').value = "";  
    6-5.  
    // replace the li inside of ul  
    function showItems(items = [], itemsList) {  
    itemsList.innerHTML = items  
    .map((elt, index) => {  
    return `<li> <input type="checkbox" id="item${index}"/> <label for="item${index}">${elt.text} </label></li>`;  
    }) //for => connect to the same id

   6-6.
   localStorage.setItem(key:string,value:string)/getItem()/removeItem();
   inspect => application => stotage => your url
   or
   inside console => print localStorage
   //yes:localStorage.setItem('items', JSON.stringify(items)); //value：items =>json-formated string
   //no:localStorage.setItem('items', items);//value：items =>string
   const items = JSON.parse(localStorage.getItem('items')) || [];
   localStorage.clear()

   6-7. so listen to common parent elt to avoid the problem,
   every time child elemnt has a change,it will rerender
   //newly added item wont be listened,following elt is from localStorage
   const checkboxs = document.querySelectorAll('input[type=checkbox]');
   checkboxs.forEach((elt) => {
   elt.addEventListener('click', handleCheckbox);
   });

   6-8. //user-defined attribute :data-index
   <input type="checkbox" data-index=${index} id="item${index}"/>
   const index = e.target.dataset.index  
   6-9. who is connected to a event，who is the “this”
