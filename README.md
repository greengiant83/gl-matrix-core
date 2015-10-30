gl-matrix-core
=========

This module wraps up @charlottegore's 3d gl-matrix components in a way that is compatible with node.js. At the time I wrote this, his npm modules couldn't be imported using require() properly due to some name issues.

## Installation

  npm install gl-matrix-core

## Usage
	
	var gl = require("gl-matrix-core");

	var v = gl.vec3.fromValues(0, 0, 1);
	var q = gl.quat.create();
	var transform = gl.mat3.create();

	console.log("v: ", v);

	gl.quat.setAxisAngle(q, gl.vec3.clone([0, 1, 0]), Math.PI / 2);
	console.log("quat: ", q);

	gl.mat3.fromQuat(transform, q);
	console.log("transform: ", transform);

	var newV = gl.vec3.create();
	gl.mat3.mul(newV, transform, v);

	console.log("newV: ", newV);
