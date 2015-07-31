# Callbacks

## Introduction


Callbacks can be used in your app when you want to open the Nous Rassemble app instead of the website on a mobile or tablet.

<aside class="warning">
Callback are not supported on desktop devices so you need to check the user agent to choose the right URL to call.
</aside>

```js
setTimeout(function () { window.location = "https://itunes.apple.com/appdir"; }, 25);
window.location = "appname://";
```

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

To display on of my proposals, call this link:

<nousrassemble://myproposals?tenantid=54f87559fa9b9e12498b456d&proposalid=5575922e529f9e292bd53cca>

<aside class="notice">
This is useful to display my pending or rejected proposals.
</aside>

### Add a proposal

<nousrassemble://proposal/add>

### Open notification panel

<nousrassemble://notifications>

### Open menu

<nousrassemble://menu>

### Open tenant selector

<nousrassemble://changesite>

### My favorites

<nousrassemble://myfavorites>

### My proposals

<nousrassemble://myproposals>

### My votes

<nousrassemble://myvotes>

### My profile

<nousrassemble://profile>

### My parameters

<nousrassemble://parameters>