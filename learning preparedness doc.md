*Learning Readiness Exercise*

*Ben Parisot*

*9/17/2018*

## Unfamiliar code

*  meta name="viewport" content="width=device-width, initial-scale=1.0"
*  const
*  what does response => response.json() do? - i think it takes whatever is in retrieved in the json during fetch and puts it into the json response?
*  what is =>
*  .textContent
* $ (tells the dom that this is jquery?)

## Curiosities
*  is lightsteelblue really a html color name?
	yes - ha, interesting
*  i didn't realize you could use then() without if()

## Script breakdown attempt

    <script>
        const ul = document.getElementById('friends'); // *construct an ul in the html document where the 'friends' id is?*
        fetch('friends.json')  // *go get 'friends.json'*
            .then(response => response.json())  // *??*
            .then(friends => {
                friends.forEach(friend => { // *loops through each element in the array*
                    const li = document.createElement('li'); // *for each element in array, create a list item*
                    li.textContent = `${friend.first} ${friend.last}`;  // *after creating the li, add in the values for friend.first and friend.last as strings?*
                    ul.appendChild(li);  // *add the new li to the end of the ul created at 'friends'*
                });
            });
    </script>

## Research answers

*  fetch // *API that provides a way for javascript to access and manipulate parts of the HTTP pipeline, like requests/responses. Still unclear about what a 'promise' is or how the response syntax works*
*  => //  *this seems to replace  { return xyz; } in order to shorten the syntax. Unsure how this bit of code would look without => though; maybe like this?*
	  *.then(response) {*
		*return response.json();*
	*}*
*  .textContent // *returns or sets the text content of whatever is being specified, in this case it would be returning the friend.first and friend.last strings from each element in the array and setting it as a single string in the li element.*
*  const // *actually a variable declaration, not a 'construct' action as I originally thought. It is declaring the ul next to it as a constant variable with the fixed reference of document.getElementByID('friends'); this means that reference can't change but the values within the reference can.*
*  <meta name="viewport" content="width=device-width, initial-scale=1.0"> // *viewport = user's visible area of the page; content =  sets the width of the page to the device width; initial-scale = sets the zoom level to 1 (default)*

## Remaining questions
*  Unsure of the fetch/response syntax. I know *what* it's doing, but I can't figure out exactly *how* it's working
