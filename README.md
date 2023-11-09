# Trabalho de sensores e permissoes 

INTRODUÇÃO

As permissões foram criadas para garantir a segurança do usuário e evitar que aplicativos maliciosos tivessem acesso fácil a sensores com potencial de colocar informações pessoais em perigo, a localização, um dos sensores mais utilizados é um ótimo exemplo da razão pelo qual é essencial que existam permissões, já que a facilidade de acesso a uma informação com esse grau de sigilo poderia resultar em diversos problemas.
Este trabalho, além de ter o objetivo de ressaltar essa importância, também tem a finalidade de apresentar as principais permissões e sensores disponíveis para Android, além dos tipos de retorno para cada sensor e lista das Actions utilizadas para cada permissão.

O QUE SÃO SENSORES?

Sensores são recursos de um dispositivo que detectam tipos de estímulos específicos e retornam um resultado que pode ou não desencadear uma ação a depender do tipo de estímulo e se o programa que solicitou o sensor determinou uma consequência ou apenas a visualização.

CATEGORIAS DE SENSORES:

Os sensores compatíveis com Android são divididos em 3 categorias principais sendo elas:

1.1
Sensores de movimento – Esses sensores monitoram diversos tipos de movimento como rotação, giro, inclinação e vibração por meio de um acelerômetro ou giroscópio, a disponibilidade desse sensor depende muito do tipo de dispositivo, uma das utilizações mais comuns é a “navegação por gestos” muito utilizada pela empresa fabricadora de celulares Motorola, que liga a lanterna ao movimentar rapidamente o smartphone 2 vezes, essa detecção é feita usando o giroscópio.
Esses sensores retornam dados tipo float, o acelerômetro retorna os dados de força da aceleração e o giroscópio dados da rotação, ambos dos 3 eixos x, y e z.

1.2
Sensores ambientais – Esses sensores monitoram diversos atributos externos do ambiente ao qual o dispositivo se encontra no momento como temperatura, umidade, pressão do ar e iluminação por meio de termômetros, barômetros(pressão do ar), higrômetro(umidade do ar) e fotômetros(iluminação). É importante ressaltar que todos esses sensores de ambiente dependem do hardware, então diferente dos de movimento que tem variação entre sensores com base em software ou hardware, esse depende exclusivamente do hardware para funcionar e é importante checar se o fabricante integrou o recurso necessário antes de utilizar. Praticamente todos os dispositivos Android possuem o termômetro, mas o barômetro é um pouco mais raro e depende do fabricante, geração, finalidade e diversos outros fatores.

Esses sensores retornam um único valor diferente dos de movimento que retornam um array float com 3 valores. Por exemplo, o termômetro retorna apenas a temperatura em graus Celsius, o barômetro retorna a pressão em hPa(hectopascal, pressão atmosférica padrão ao nível médio do mar), o higrômetro retornam a umidade em porcentagem(%) e fotômetro que retorna a taxa de luminosidade em lx(quantidade de luz por metro quadrado).

1.3
Sensores de posição – Esses sensores monitoram a posição física do dispositivo, o Android oferece dois sensores para essa categoria sendo eles: sensor de campo geomagnético e o acelerômetro, também utilizado nos de movimento como citado anteriormente. Assim como os sensores ambientais, os de posição são baseados no hardware, a diferença é que a maioria dos fabricantes inclui os 2 sensores já que são usados para finalidades básicas que existem desde o começo da utilização dos smartphones, tablets e dispositivos Android no geral. Um exemplo de utilização comum desse sensor é o desligamento automático da tela ao executar ligações e direcionar o dispositivo ao ouvido ou até mesmo o recurso adiciona recentemente de manter o celular desbloqueado quando estiver no bolso, os dois exemplos para determinar a proximidade do dispositivo utilizam esses sensores.

Como explicado nos 1.1, o acelerômetro retorna dados tipo float para a força da aceleração e o sensor de campo geomagnético também retorna dados dos 3 eixos, x, y e z, mas em referência a intensidade da proximidade do dispositivo em comparação a um campo magnético, no caso do exemplo das ligações eletrônicas, a pessoa.

SENSORES DE MOVIMENTO:

TYPE_ACCELEROMETER baseado em hardware, utiliza o acelerômetro, retornando a força da aceleração nos 3 eixos incluindo a força da gravidade. Comumente utilizado para detectar movimentos de rotação, giro, inclinação e vibração.

TYPE_GYROSCOPE baseado em hardware, utiliza o giroscópio, retornando a taxa de rotação do dispositivo em rad/s(radiano por segundo, divisão entre o deslocamente do dispositivo pelo raio da circunferência da rotação) nos 3 eixos. Muito utilizado na “navegação por gestos” dos dispositivos em ações como rotacionar o dispositivo para abrir a câmera.

TYPE_GRAVITY baseado em software ou hardware, utiliza o giroscópio, retornando a força da gravidade nos 3 eixos, detecta a agitação, inclinação, rotação. Também utilizado na “navegação por gestos”.

TYPE_LINEAR_ACCELERATION baseado em software ou hardware, utiliza o acelerômetro, retornando a força da aceleração em um único eixo excluindo a força da gravidade.

TYPE_ROTATION_VECTOR baseado em software ou hardware, utiliza o giroscópio, retornado a rotação do dispositivo nos 3 eixos em forma de vetor.

SENSORES AMBIENTAIS:

TYPE_AMBIENT_TEMPERATURE baseado em hardware, utiliza o termômetro, retornando a temperatura do ambiente em graus Celsius.

TYPE_LIGHT baseado em hardware, utiliza o fotômetro, retornando o nivel d eluz do ambiente em lx(quantidade de luz por metro quadrado), detecta e controla o brilho da tela, utilizado em recursos como “moto noturno” que diminui o brilho a depender da luz ambiente.

TYPE_PRESSURE baseado em hardware, utiliza o barômetro, retornando a pressão do ar em hPa(hectopascal, pressão atmosférica padrão ao nível médio do mar).

TYPE_RELATIVE_HUMIDITY baseado em hardware, mede a umidade relativa do ar em porcentagem, detecta o ponto de condensação, umidade absoluta e relativa.

TYPE_TEMPERATURE baseado em hardware, utiliza o termômetro, retornando a temperatura da CPU do dispositivo em graus Celsius. Importante ressaltar que esse sensor foi substituído pelo TYPE_AMBIENT_TEMPERATURE no API 14 do Android.

SENSORES DE POSIÇÃO:

TYPE_MAGNETIC_FIELD baseado em hardware, utiliza o sensor de campo geomagnético para medir o campo geomagnético do ambiente nos 3 eixos e criar uma bussola. Retorna o valor em μT(micro-Tesla), unidade de medida utilizada para densidade de fluxo magnético.

TYPE_ORIENTATION baseado em software, mede os graus de rotação nos 3 eixos e determina a posição do dispositivo. Foi depreciado na versão Android 2.2 e o tipo foi descontinuado no Android 4.4. Atualmente, esse sensor pode ser obtido por meio de uma combinação do sensor TYPE_MAGNETIC_FIELD e TYPE_ACCELEROMETER.

TYPE_PROXIMITY baseado em hardware, utiliza o sensor de campo geomagnético, mede a proximidade da tela do dispositivo em comparação a um campo magnético, objeto. Esse sensor é comumente utilizado para detectar se o smartphone está próximo ao ouvido de uma pessoa durante uma ligação e a deligar a tela.

CONCLUSÃO

BIBLIOGRAFIA
https://developer.android.com/guide/topics/sensors/sensors_overview?hl=pt-br
https://developer.android.com/training/permissions/requesting?hl=pt-br
https://developer.android.com/guide/topics/permissions/overview?hl=pt-br
https://developer.android.com/guide/topics/sensors?hl=pt-br
