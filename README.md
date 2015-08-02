# Wavelert
Windows 98 style javascript prompts.
![lol](https://raw.github.com/lawwrr/Wavelert/master/screenshot.gif)

## But…why?
Regular alerts just look worse and less cool than they used to. Also, I wanted to use ES6 syntax for *something*

## ES6 browser usage
With jQuery already loaded, import either alert or confirm, then init it and place() it on the html. You don't need wavelert.min.js

	import {Alert}   from 'wavelert/alert';
	import {Confirm} from 'wavelert/confirm';
	
	var cf = new Confirm('Are you sure?').place()
	cf.success(function(){
        new Alert('✨ all is good ✨');
    })
    cf.fail(function(){
        new Alert('💩 you dismissed the alert 💩');
	});

## Legacy browser usage
Add dist/wavelert.min.js after jquery. Wavelert requires jQuery because I'm too lazy to use queryselector so you'll have to deal with that, sorry.

Check the [live demo](http://lawwrr.github.io/Wavelert/) for details

	$('.🆒').on('click',function(){
		wavelert.confirm({
			title: 'Wololo',
			dark: true,
			icon: 'alert'
		}).success(function(){
            wavelert.alert('✨ all is good ✨');
        }).fail(function(){
            wavelert.alert('💩 you dismissed the alert 💩');
		})
	});

## Building
Just install gulp if you don't have it already

	sudo npm install --global gulp

Then gulp everything whenever you want to see changes

	sudo npm install
	gulp
