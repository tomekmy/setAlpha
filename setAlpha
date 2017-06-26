function setAlpha(photo, r, g, b) {
	// Get the image
	var img = document.getElementById(photo);
	document.body.appendChild(img);
	// Create cnavas element
	var canvas = document.createElement('canvas');
	// Set cnavas width and height to natural dimentions of photo
	canvas.width = img.naturalWidth;
	canvas.height = img.naturalHeight;
	// Add canvas element to the DOM
	document.body.appendChild(canvas);
	// Put photo into the canvas
	var ctx = canvas.getContext('2d');
	ctx.drawImage(img, 0, 0);
	// Get canvas data
	var image = ctx.getImageData(0, 0, canvas.width, canvas.height);
	var imageData = image.data;
	// Loop through all pixels and if pixel color equals rgb(255, 255, 255), white set its alpha to 0 else
	// get the max new width and height of canvas
	for (i = 0; i < imageData.length; i += 4) {  
			if(imageData[i] === r && imageData[i+1] === g && imageData[i+2] === b) {
					imageData[i+3] = 0;
			}
	}
	// After the manipulation, reset the data
	image.data = imageData;
	// And put the imagedata back to the canvas
	ctx.putImageData(image, 0, 0);
	// Send canvas with alpha to trimImg function and put trimed canvas back into this function canvas
	canvas = trimImg(canvas);
	// Finaly send base64 photo src
	var img_src = canvas.toDataURL();
	// Remove photo and canvas from DOM
	return img_src;
}
