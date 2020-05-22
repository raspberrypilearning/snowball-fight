## बर्फ़गोले बनाना

चलिए बर्फ़गोले बनाते है ताकि हम उसे स्टेज (stage) के आस पास फ़ेंक सकें |

--- task ---

Scratch स्टार्टर प्रोजेक्ट खोलें।

**ऑनलाइन**: [स्टार्टर प्रोजेक्ट खोलें](http://rpf.io/snowball-fight-on){:target="_blank"} |

यदि आपके पास एक Scratch खाता (account) है तो आप **Remix** पर क्लिक करके प्रतिलिपि बना सकते हैं |

**ऑफलाइन**: [स्टार्टर प्रोजेक्ट](http://rpf.io/p/en/snowball-fight-go){:target="_blank"} को ऑफलाइन एडिटर (offline editor) में खोलिये।

यदि आपको Scratch ऑफ़लाइन एडिटर को डाउनलोड और इंस्टॉल (download and install) करने की आवश्यकता है तो आप इसे [rpf.io/scratchoff](http://rpf.io/scratchoff){:target="_blank"} पर पा सकते हैं।

In the starter project, you should see a blank stage and snowball sprite.

--- /task ---

--- task ---

'बर्फ़गोला' स्प्राइट के 2 पोशाक (costumes) है| एक सामान्य पोशाक है और एक है जिसमें दिखाया गया है कि बर्फ़गोला किस दिशा में जाएगा।

![snowball costumes](images/snow-costume.png)

--- /task ---

--- task ---

सबसे पहले आइए खिलाड़ी को बर्फ़गोला के कोण (angle) को बदलने की अनुमति दें। Add this code to your snowball sprite:

![snowball sprite](images/snowball-sprite.png)

```blocks3
when flag clicked
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (snowball-aim v)
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
```

--- /task ---

--- task ---

हरे झंडे पर क्लिक करके अपने प्रोजेक्ट का परीक्षण करें। You should see that your snowball follows the mouse, until you press the mouse button.

![snow ball aim sprite pointing at mouse pointed](images/snow-mouse.png)

--- /task ---

--- task ---

आइए खिलाड़ी को यह तय करने की भी अनुमति दें कि बर्फ़गोला को कितनी ताकत से फेंकना चाहिए। Create a new variable called `power`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

--- /task ---

--- task ---

Drag your new variable display to the bottom of the stage, near the snowball. स्टेज पर वेरिएबल प्रदर्शक(display) पर राइट क्लिक करें और 'slider' पर क्लिक करें।

![variable changed to slider](images/snow-slider.png)

--- /task ---

--- task ---

Add code to set your new `power`{:class="block3variables"} variable to 0 when the flag is clicked.

![snowball sprite](images/snowball-sprite.png)

```blocks3
when flag clicked
+ set [power v] to (0)
```

--- /task ---

--- task ---

अब आपके पास `power` {"class =" block3variables "} वेरिएबल है, अब आप बर्फ़गोले की शक्ति बढ़ा सकते हैं लेकिन सिर्फ़ नीचे दिए गए कोड से दिशा चुनने के _बाद_ ही:

![snowball sprite](images/snowball-sprite.png)

```blocks3
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
+repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [power v] by (1)
    wait (0.1) seconds
end
```

इस कोड का मतलब है कि आपको _माउस बटन को दबाकर रखना है_ दिशा चुनने के बाद, बर्फ़गोला की शक्ति को चुनने के लिए।

--- /task ---

--- task ---

Test your snowball, to see if you can choose its angle and power.

![power variable at 35 next to snowball aim](images/snow-test.png)

--- /task ---
