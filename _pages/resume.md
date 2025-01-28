---
permalink: /resume/
layout: default

title: Resume
description: Cameron's Resume
---


<div class="content flex flex-column justify-items-center">
	<div class="align-items-center justify-items-center" style="display:grid;">
        <object class="title-image" style="height:57.5%;" data="/assets/images/Resume_Logo_Active.svg" type="image/svg+xml"></object>
    </div>
    <div class="border flex flex-column border-radius-lg self-center" style="display:inline-block; width:98%">
        <div class="border-radius-lg" id="adobe-dc-view"></div>
		<script src="https://acrobatservices.adobe.com/view-sdk/viewer.js"></script>
		<script type="text/javascript">
			document.addEventListener("adobe_dc_view_sdk.ready", function(){ 
				var adobeDCView = new AdobeDC.View({clientId: "eac548ae89c941ffbbb543b2012b486b", divId: "adobe-dc-view"});
				adobeDCView.previewFile({
					content:{location: {url: "/assets/images/CameronMeyer_TechnicalArtist_Resume.pdf"}},
					metaData:{fileName: "CameronMeyer_TechnicalArtist_Resume.pdf"}
				}, {embedMode: "IN_LINE"});
			});
		</script>
    </div>
</div>

<div class="pt-12"></div>