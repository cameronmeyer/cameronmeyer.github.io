---
permalink: /resume/
layout: default

title: Resume
description: Cameron's Resume
---


<div class="flex flex-column">
    <div style="display: grid;">
        <object class="title-image" data="/assets/images/AboutMe.svg" type="image/svg+xml"></object>
    </div>
    <div class="border flex flex-row border-radius-lg self-center" style="display:inline-block">
        <div class="border-radius-lg" id="adobe-dc-view" style="width: 800px;"></div>
		<script src="https://acrobatservices.adobe.com/view-sdk/viewer.js"></script>
		<script type="text/javascript">
			document.addEventListener("adobe_dc_view_sdk.ready", function(){ 
				var adobeDCView = new AdobeDC.View({clientId: "eac548ae89c941ffbbb543b2012b486b", divId: "adobe-dc-view"});
				adobeDCView.previewFile({
					content:{location: {url: "/assets/images/Resume.pdf"}},
					metaData:{fileName: "Resume.pdf"}
				}, {embedMode: "IN_LINE"});
			});
		</script>
    </div>
</div>

<div class="pt-12"></div>