#Commitment

A simple, lightweight jQuery plugin used to display commit messages for a specific Github repository.

<a href="http://michael-lynch.github.io/commitment/" target="_blank">See a demo</a>

##Instructions

Include jQuery and the plugin in the head or footer of your page.

```html
<script src="//ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script>
    
<script src="/js/plugins/commitment.js"></script>
```
    
Create an ordered or unordered list and assign it a class or ID.

```html
<ul id="commits"></ul>
```
    
Initialize the plugin targeting the class, ID or element that will contain the commit messages, and set the "user" and "repo" properties of the repository you wish to display the commit messages of. 

```js
$('#commits').commitment({
    user: 'michael-lynch',
    repo: 'reading-time'
});
```
	
####Options

<p><em>user</em>: string (required)
<br />A string that defines the Github username (default: null).
</p>

<p><em>repo</em>: string (required)
<br />A string that defines the Github repository (default: null). 
</p>

<p><em>filterBranch</em>: string / sha
<br />A string that defines either a branch name or SHA that will be used to filter the commit messages (default: null).
</p>

<p><em>filterAuthor</em>: string
<br />A string that defines a Github username that will be used to filter the commit messages (default: null).
</p>

<p><em>filterPath</em>: string
<br />A string that defines a path that is to be required in the commits being returned (default: null).
</p>

<p><em>filterSince</em>: ISO timestamp (YYYY-MM-DDTHH:MM:SSZ)
<br />A timestamp that defines the start date of the commit messages being returned (default: null).
</p>

<p><em>filterUntil</em>: ISO timestamp (YYYY-MM-DDTHH:MM:SSZ)
<br />A timestamp that defines the end date of the commit messages being returned (default: null).
</p>

<p><em>makeCommitLink</em>: boolean
<br />A boolean value that indicates whether or not the commit message should be a link (default: false).
</p>

<p><em>showCommitDate</em>: boolean
<br />A boolean value that indicates whether or not the date of the commit message should be displayed (default: true).
</p>

<p><em>dateFormat</em>: "dd/mm/yyyy"
<br />A specific string that defines the format of the commit message date (default: null).
</p>

<p><em>showCommitter</em>: boolean
<br />A boolean value that indicates whether or not the committer should be displayed (default: true).
</p>

<p><em>showCommitterAvatar</em>: boolean
<br />A boolean value that indicates whether or not the commiter avatar should be displayed (default: true).
<br /><em>* showCommitter is required to be set to true to use showCommitterAvatar</em>
</p>

<p><em>success</em>: function() {}
<br />A function that runs after the plugin has successfully retrieved the commit messages. (default: function()).
</p>

<p><em>error</em>: function() {}
<br />A function that runs if there was an error retrieving the commit messages. (default: function(message)).
</p>

#####Example:

```js
$(function() {

	$('#commits').commitment({
		user: 'michael-lynch',
		repo: 'reading-time',
		success: function() {
		    console.log('Commit messages were successfuly retrieved from Github!');
		},
		error: function(message) {
		    console.log(message);
		}
	});	
});
```