node('docker') {
	// Build the Jenkinsfiles

	 stage name: "Checkout";
     checkout scm;

     step([$class: 'DockerBuilderPublisher', 
     	cleanImages: true, 
     	cleanupWithJenkinsJobDelete: true, 
     	dockerFileDirectory: 'hello', 
     	tagsString: "hello-world-hello",
     	pushOnSuccess: false]);

     step([$class: 'DockerBuilderPublisher', 
     	cleanImages: true, 
     	cleanupWithJenkinsJobDelete: true, 
     	dockerFileDirectory: 'world', 
     	tagsString: "hello-world-world",
     	pushOnSuccess: false]);

	step([$class: 'DockerBuilderPublisher', 
     	cleanImages: true, 
     	cleanupWithJenkinsJobDelete: true, 
     	dockerFileDirectory: 'frontend', 
     	tagsString: "hello-world-frontend",
     	pushOnSuccess: false]);    

    step([$class: 'SnowGlobeStep', action: 'create', source: [$class: 'GlobeSourceFile', file: 'snowglobe/snowglobe.sg', name: 'main']]) 	
}