# Callbacks

## Introduction


Callbacks can be used in your app when you want to open the Nous Rassemble app instead of the website on a mobile or tablet.

<aside class="warning">
Callback are not supported on desktop devices so you need to check the user agent to choose the right URL to call.
</aside>

<pre><code>
setTimeout(
	function () {
		window.location = "https://www.nousrassemble.com";
	} , 25
);
window.location = "nousrassemble://home";
</code></pre>

<aside class="notice">
You need to call the website too on a mobile or tablet if App is not installed.
Here is a trick you can use.
You can try redirecting the phone to the app, and if nothing happens redirect the phone to a specified page, like this:
</aside>


## Query Parameters

In callbacks below, you need to inject the tenant ID or a proposal ID.

Parameter | Description
--------- | -----------
`tenantid`  | The ID of the tenant related with your call
`proposalid` | The ID of the proposal related with your call


## Endpoints

### Tenant home

To go to the tenant home page, call this link:

<nousrassemble://home?tenantid=54f87559fa9b9e12498b456d>

---

### Proposal

To display a proposal, call this link:

<nousrassemble://proposal?tenantid=54f87559fa9b9e12498b456d&proposalid=5575922e529f9e292bd53cca>

<aside class="notice">
You can go to the first comment by appending the hash <code>#timeline</code> to the URL:<br/>
<a href="nousrassemble://proposal?tenantid=54f87559fa9b9e12498b456d&proposalid=5575922e529f9e292bd53cca#timeline">nousrassemble://proposal?tenantid=54f87559fa9b9e12498b456d&proposalid=5575922e529f9e292bd53cca#timeline</a>
</aside>


### My proposal

To go to user proposals page, call this link:

<nousrassemble://myproposals?tenantid=54f87559fa9b9e12498b456d&proposalid=5575922e529f9e292bd53cca>

<aside class="notice">
This is useful to display my pending or rejected proposals.
</aside>

### My favorites

To go to user favorites page, call this link:

<nousrassemble://myfavorites>

### My votes

To go to the page of proposals for which user has voted, call this link:

<nousrassemble://myvotes>

### Add a proposal

To go to the new proposal form, call this link:

<nousrassemble://proposal/add?tenantid=54f87559fa9b9e12498b456d>

### Open notification panel

To go to home with the notifications right panel opened, call this link:

<nousrassemble://notifications>

### Open menu

To go to home with the menu left panel opened, call this link:

<nousrassemble://menu>

### Open tenant selector

To go to home with the tenant selector opened on top, call this link:

<nousrassemble://changesite>

### My profile

To go to the user profile page, call this link:

<nousrassemble://profile>

### My parameters

To go to the user settings page, call this link:

<nousrassemble://parameters>