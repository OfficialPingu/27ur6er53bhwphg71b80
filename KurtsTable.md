# Kurts' Table Documentation.
I know this may be a little off-topic for any viewers, but coincidentally - I love polybius squares. I have designed my own passworded polybius-derived cipher that I often use to communicate securely with just about anyone I feel needs secure talking to.

If a viewer like you needs to understand what I'm trying to tell you in dire circumstances, I have created this documentation on how to understand my cipher text.

To begin, I have created an online aid to help in converting polybius coordinates to characters in my alphabet or vice versa, see [Kurts Table Aid](https://chib.xyz/polybius/kurttable.html).

So, how does it work with a password? Let me explain.

When I encrypt the text "this is some experimental text" using the password "password", I will get "9p8.r4 )@w5xr0/01z8582.l8%,xe@" in return.

Imagine the polybius table as a cartesian plane, where each cell is a coordinate. Having X values from 0-7, and Y values from 0-7. Every combination of these coordinates has a character in the alphabet provided.

Using the table aid link I provided above, I can convert this string into a set of coordinates on this cartesian plane, as such;

16 23 75 36 43 35 26 67 76 24 45 34 43 64 77 64 74 54 75 45 75 15 36 52 75 37 46 34 51 76

Keep in mind that each individual number holds a digit for the X and Y coordinates in the alphabet square; 45 has X-coordinate 4 and Y-coordinate 5.

If I do the same thing to the password "password", I will get these coordinates in return;

23 11 53 53 24 13 43 41

Now that we have the square's coordinates drawn out for both the cipher text and the known password, the next step we must do is match the length, or number of coordinates, of the password to the cipher text. If the password is longer than the cipher text - you cut it short. Otherwise, you repeat the passwords coordinates over until the length matches that of the cipher text. As such;

txt: 16 23 75 36 43 35 26 67 76 24 45 34 43 64 77 64 74 54 75 45 75 15 36 52 75 37 46 34 51 76

key: 23 11 53 53 24 13 43 41 23 11 53 53 24 13 43 41 23 11 53 53 24 13 43 41 23 11 53 53 24 13

And now for the fun part; you must subtract the keys coordinates from the cipher texts coordinates at each of their corresponding indexes. Keep in mind, if the resulting value is less than 1 or greater than 7 (the minimum and maximum values of the alphabets square, either vertically or horizontally depending on whether or not the value is for the X coordinate or Y coordinate), then you should wrap the number around. For example, -2 would become 5, 0 would become 7, and 8 would become 1. Here is an example of combining the cipher text to the key text;

txt: 16 23 75 36 43 35 26 67 76 24 45 34 43 64 77 64 74 54 75 45 75 15 36 52 75 37 46 34 51 76

key: 23 11 53 53 24 13 43 41 23 11 53 53 24 13 43 41 23 11 53 53 24 13 43 41 23 11 53 53 24 13

com: 63 12 22 53 26 22 53 26 53 13 62 51 26 51 34 23 51 43 22 62 51 72 63 11 52 26 63 51 34 63

Finally, plot these combined coordinates into my square found at [Kurts Table Aid](https://chib.xyz/polybius/kurttable.html) and it should result in "this is some experimental text"!

Go ahead and try it yourself, it will get easier the more you try it. As a practise run, try and decrypt the text "@vvv6fgwk4x4?x!d3mk" with password "pass1234".

Good Luck!
Kurt Koller ~
