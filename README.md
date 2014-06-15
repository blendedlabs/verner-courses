# Verner courses

## Course creation instructions

 * List of courses is kept in courses.json. Format:
   * **name**: Name of the course
   * **imageUrl**: Relative url of the course cover image, ~ 320x240px. Jpeg & Png supported.
   * **courseUrl**: Relative url of the course contents json (see below).

 * Course contents file is kept in f.ex. yura-course/course.json. Format:
   * **name**: Name of the course (should be the same as in courses.json).
   * **slides**: Array of course slides. Format of slide (all parameters optional):
     * **heading**: Slide heading
     * **text** or **body**: Main slide text or question.
     * **imageUrl**: Relative url of background slide picture, ~500x700. Will be resized as needed to fill the screen.
     * **topImageUrl**: Url of picture shown above heading/text. Will be resized to full width.
     * **bottomImageUrl**: Url of picture shown below text.
     * **backgroundColor**: Color of the background, in usual CSS format (#abcdef)
     * **textColor**: Color of main text.
     * **answers**: Array of possible answers. Format:
       * **text**: Answer text.
       * **correct**: Is this answer correct (true or false, without quotes).
       * **hint**: Text to show to the user when they've chosen this answer.
     * **buttons**: Array of buttons. Format:
       * **text**: Button text.
       * **action**: Either a full url to open in browser, or 'close' - to close the course.


## Sample 

```json
{
    "name": "Yura's course",
    "slides": [
        { "heading": "Hello Yura!", "text": "This is our first slide" },
        { "text": "Welcome to our first course! Yo!" },
        { "text": "A background can be changed like this", "backgroundColor": "#3e313c", "textColor": "#ffffff" },
        { "text": "Do you like it?", "topImageUrl": "0-question-small.png", "answers": [
            {"text": "Totally!", "hint": "Really?"}, 
            {"text": "Not really", "hint": "Wrong!!"}, 
            {"text": "You bet!", "correct": true, "hint": "Congratulations!"},
            {"text": "What was the question again?"}
        ]},
        { "text": "And here is\n how to do\n multiline \n \n Course update test" },
        { "text": "You can even use a picture with this text!", "imageUrl": "imagesample.jpg", "textColor": "#ffffff" },
        { "text": "That's all for now! See github and create something awesome!", "buttons": [
            {"text": "Open GitHub repo", "action": "https://github.com/ashtuchkin/maester-courses"},
            {"text": "Back to Course List", "action": "close"}
        ]}
    ]
}
```





