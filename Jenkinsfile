def get = new URL("https://e3a00cee-f097-45a1-a303-2a761173ae2d.mock.pstmn.io/prueba500").openConnection();
def getRC = get.getResponseCode();

pipeline {
    agent any 
    stages {
        stage('Api test') {
            steps {
                //echo 'Hello world!' 
                // GET

                println(getRC);
                if(getRC.equals(200)) {
                    println(get.getInputStream().getText());
                }
            }
        }
    }
}









