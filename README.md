MATHEUS GARCIA e MARIA CLARA 

Na atividade foi pedida a adição de sensores em aplicativos já realizados anteriormente em atividades propostas em bimestres passados, porem devido ao peso da plataforma Android Studio, ambos computadores da dupla não foram capazes rodar o mesmo incapacitando a colocar dos códigos pedidos em aula em prática, diante disto, segue em anexo os devidos códigos para a realização dos sensores, tal como o que na plataforma seria equivalente a comentários com a sua descrição. 

Fora do OneCreate  

SensorManager sensorManager;
    Sensor sensor;

Dentro do OneCreate


            sensorManager = (SensorManager) getSystemService(SENSOR_SERVICE); // Acessar os sensores da plataforma 
            sensor = sensorManager.getDefaultSensor(Sensor.TYPE_ACCELEROMETER); // Acessar o sensor de acelerômetro que será utilizado para alterar imagens após balançar o dispositivo 

            // Atraso de resposta do sensor
            sensorManager.registerListener(Perfil.this, sensor, sensorManager.SENSOR_DELAY_NORMAL);


USANDO O SENSOR

    @Override
    public void onSensorChanged(SensorEvent event) {
        float x = event.values[0];

        if (x > 18) {
            img_Random(); // Função para mudar a imagem do usuário após movimentos 
            mensagem_sensor(); // Função para toast (mensagem a ser apresentada) 
        }
    }

    private void img_Random() {
        int[] imgs = {
                R.drawable.img1,
                R.drawable.img2,
                R.drawable.img3,
                R.drawable.img4,
                R.drawable.img5,
                R.drawable.img6
        }; // Array com os nomes da imagens, que seriam alteradas com o movimento.

        Random random = new Random(); // Gera um número aleatório, para que a imagem (que possui um valor de int para ser numerada) seja alterada de acordo com a numeração 
        int random_imgs = random.nextInt(imgs.length); // Gera um número aleatório com no máximo o número de imagens

        img_avatar.setImageResource(pets[random_Pet]); // Muda a imagem de acordo com o número
    }
