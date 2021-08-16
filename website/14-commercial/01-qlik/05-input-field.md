---
layout: page
title: Qlik Sense 3.0 Input field Example
description: Qlik Sense 3.0 Input field Example
keywords: Qlik Sense 3.0 Input field Example
permalink: /commercial/qlik/3.x/input-field/
---

# [Qlik Sense 3.0] Input field Example

    define(["qlik"], function(qlik) {

    	return {

    		paint : function($element, layout) {
    			var html = "";
    			var ext = this;

    			html += '<table><tr><td><input type="text"/></td></tr></table>';

    			$element.html(html);

    			$element.find('input').on('change', function() {

    				var val = $(this).val() + '';
    				console.log(val);
    			});
    		}
    	};
    });
