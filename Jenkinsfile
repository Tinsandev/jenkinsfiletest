pipeline {
    agent any 
    stages {
        stage('Api test') {
            steps {
                //echo 'Hello world!' 
                // GET
                script {
                    def get = new URL("https://e3a00cee-f097-45a1-a303-2a761173ae2d.mock.pstmn.io/prueba500").openConnection();
                    def getRC = get.getResponseCode();


                      def remote = [:]
                      remote.name = 'test'
                      remote.host = '172.17.0.4'
                      remote.user = 'root'
                      remote.password = 'root'
                      remote.allowAnyHosts = true

                    println(getRC);
                    if(getRC.equals(200)) {
                        println("API OK");
                    }
                    else {
                        println("API no disponible");

                        sshCommand remote: remote, command: "ls -lrt"
                        sshCommand remote: remote, command: "for i in {1..5}; do echo -n \"Loop \$i \"; date ; sleep 1; done"

                    }





                }
            }
        }
    }
}