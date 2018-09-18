# interview-test-project

* Candidate has to design single webpage.
* HTML markup should go in `index.html`
* CSS rules should go in `css/style.css`
* JavaScript should go in `js/script.js`
* Images should go in `images/` directory.
* If candiate want to use `Bootstrap-3`, then its minified css is already loaded from CDN on `index.html` page.


I can see there are manual changes in `Poll` contrib module.

* `Contrib module: Polls`
* `File path: poll/src/Form/PollViewForm.php`
* `line #: 111`

This line gives call to `function getProspectUserAccessPointerForm()` which is defined in `mainebiz.theme` file.

I load `PollViewForm` in enews. When accessed as `anonymously` the above line of code tries to resolve `function getProspectUserAccessPointerForm()` under namespace `Drupal\poll\Form\`

Please check with your team if they need this line of code. If yes, then please ask them to fix the namespace issue.

Detailed issue:
`Error: Call to undefined function Drupal\poll\Form\getProspectUserAccessPointerForm() in Drupal\poll\Form\PollViewForm->buildForm() (line 111 of modules/contrib/poll/src/Form/PollViewForm.php).`


Commit Reference which introduce `line #111`:

`96d93f7 - soumalya-webonise <soumalya-webonise@github.com> 26 Jul, 2018
Prospect user Form implementation in frontend for poll respond and comment`
