node('docker') {
	// Build the Jenkinsfiles

     stage name: "Checkout";
     checkout scm;

     stage name: "Build Docker Images"
     build_docker_image('hello');
     build_docker_image('world');
     build_docker_image('frontend');
     

     stage name: "Register Snowglobe"
     snowglobe().fromFile("snowglobe/snowglobe.sg")
          .register().exec();          
}

def build_docker_image(String name) {
     step([$class: 'DockerBuilderPublisher', 
          cleanImages: false, 
          cleanupWithJenkinsJobDelete: true, 
          dockerFileDirectory: name, 
          tagsString: "hello-world-${name}",
          pushOnSuccess: false]);
}