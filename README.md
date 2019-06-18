
# frappe-summernote

# Guide to getting back original Text Editor - Summernote

In Frappe v11 release Summer Note text editor was replaced with Quill. This broke our website built through frappe/even Email signatures. In both we were using text editor field and we edited content through HTML Code in summernote, which changed automatically in Quill.

Given the fact we like to build rich website interface/Email Templates/print formats using same default text editor fields which user can also use to change content of some page, we liked Summer Note ability to change code through HTML code editor. So we decided to go back to Summer Note

If anyone like us want to go back to Summer Note through custom app, here is a Simple Guide you can follow to effortlessly to retrieve back your old editor.

**Step: 1**
First, if your app doesn’t have a public folder inside frappe-`bench/apps/custom_app/custom_app/` then create it.

**Step: 2**
Now, in your public folder, create another folder called js and place the respective files in the specified folders.

text_editor.js -> `../public/js/frappe/form/controls/text_editor.js	`

timeline.js -> `../public/js/frappe/form/footer/timeline.js`	

comment.js -> `../public/js/frappe/ui/comment.js	`

summernote.js -> `../public/js/lib/summernote/summernote.js	`

summernote.css -> `../public/js/lib/summernote/summernote.css`

**Step: 3**
Now, place the build.json file in your public folder.

**Step: 4**
In your hooks.py include the following code:

`app_include_js = [

	"assets/js/summernote.min.js",

	"assets/js/comment_desk.min.js",`

`	"assets/js/editor.min.js",`

`	"assets/js/timeline.min.js"`

`]`

`app_include_css = [`

`	"assets/css/summernote.min.css"`

`]`

**Step: 5**
After completing all the above steps, execute the following commands:

`bench migrate` 

`bench restart` 

`bench build`


Now, you will be able to see your OLD Text Editor - SUMMER NOTE
