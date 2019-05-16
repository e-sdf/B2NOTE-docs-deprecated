# Widget

DRAFT

B2NOTE widget can be integrated into web application using these options:

- embedded `div` and `iframe` within your web application, where b2note widget can be displayed.
- pop-up window opened next to your window


## Embedded DIV and IFRAME  
This option integrates b2note widget directly into your web application. You can design it to disappear after it's not needed anymore.

The following example expects:
- `mywebapp.html` is hosted by your web application
- the code will open the iframe with content hosted by b2note web application `interface_main.html`.

Within `mywebapp.html`, place the following `iframe`:
```html
  <div id="b2note" style="float:right;width:30%">
    <iframe id="b2note_iframe" name="b2note_iframe" src="" style="width: 100%; height: 600px; border: 1px solid grey;"></iframe>
  </div>
```
The `<div>` places the iframe and set's it's style to float to right.
The `<iframe>` is empty, set's the `1px` border and height `600px`.

Further in `mywebapp.html` you may decide that some link to a resource/file is
desirable for annotation, thus place the following form:
```html
  <form id="b2note_form_" action="https://b2note.bsc.es/interface_main.html" method="post" target="b2note_iframe" onSubmit='togglewidgeton()'>
                <input type="hidden" name="recordurl_tofeed" value='https%3A%2F%2Ftrng-b2share.eudat.eu%2Frecords%2F3894dfbf97a44e04814fb986f56c87ce' className="field left" readOnly="readonly"/>
                <input type="hidden" name="pid_tofeed" value='http%3A%2F%2Fhdl.handle.net%2F0000%2F3894dfbf97a44e04814fb986f56c87ce' className="field left" readOnly="readonly"/>
                <input type="hidden" name="subject_tofeed" value='https%3A%2F%2Ftrng-b2share.eudat.eu%2Fapi%2Ffiles%2Ff2b09dd8-a524-49e4-a7d3-100d830895b7%2FtestFile.txt' className="field left" readOnly="readonly"/>
                <input type="hidden" name="keywords_tofeed" value='' className="field left" readOnly="readonly"/>
                <input type="submit" className="btn btn-sm btn-default" value="Annotate in B2Note" title="Click to annotate file using B2Note."/>
  </form>
```
This form just creates a button, after clicking it, it sends POST request with fields bellow and the response (html content) is then placed into the iframe with id `b2note_iframe` defined above.
- `subject_tofeed` contains direct link to annotated resource - it is expected that this link will download the content
- `recordurl_tofeed` contains container resource, e.g. landing page.
- `pid_tofeed` may contain unique URL to the resource.

You can place as many as possible forms with buttons as needed - differing only in some of the fields `subject_tofeed` and `pid_tofeed`. 

## Popup window
This option doesn't need to design or reserve some space within your web application.
Within `mywebapp.html` or in some included script put the following javascript code:
```javascript

function popupwindow(formid){ //- id of form element with b2note data fields
    var mapForm = document.getElementById(formid);
    map=window.open("","b2notewin","status=0,title=0,height=600,width=300,scrollbars=1,menubar=0,status=0");
   if (map) {
      mapForm.submit();
   } else {
      alert('You must allow popups for this map to work.');
   }
}
```
This code will create pop-up window and submit the data into b2note widget

Further in `mywebapp.html` you may decide that some link to a resource/file is
desirable for annotation, thus place the following form:
```html
  <form id="b2note_form3" action="https://b2note.bsc.es/interface_main.html" method="post" target="b2notewin" onSubmit='popupwindow("b2note_form3")'>
                <input type="hidden" name="recordurl_tofeed" value='https%3A%2F%2Ftrng-b2share.eudat.eu%2Frecords%2F3894dfbf97a44e04814fb986f56c87ce' className="field left" readOnly="readonly"/>
                <input type="hidden" name="pid_tofeed" value='http%3A%2F%2Fhdl.handle.net%2F0000%2F3894dfbf97a44e04814fb986f56c87ce' className="field left" readOnly="readonly"/>
                <input type="hidden" name="subject_tofeed" value='https%3A%2F%2Ftrng-b2share.eudat.eu%2Fapi%2Ffiles%2Ff2b09dd8-a524-49e4-a7d3-100d830895b7%2FtestFile.txt' className="field left" readOnly="readonly"/>
                <input type="hidden" name="keywords_tofeed" value='' className="field left" readOnly="readonly"/>
                <input type="submit" className="btn btn-sm btn-default" value="Annotate in popup B2Note" title="Click to annotate file using B2Note."/>
  </form>
```
This form just creates a button, after clicking it, it sends POST request with fields bellow and the response (html content) is then placed into the popup window `b2note_form3` opened by script.
- `subject_tofeed` contains direct link to annotated resource - it is expected that this link will download the content
- `recordurl_tofeed` contains container resource, e.g. landing page.
- `pid_tofeed` may contain unique URL to the resource.

You can place as many as possible forms with buttons as needed - differing in `<form id='xx'>` and fields `subject_tofeed` and `pid_tofeed`. 
