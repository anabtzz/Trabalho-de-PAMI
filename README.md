<h1 align=center> TRABALHO DE SENSORES E PERMISSÕES </h1>
<h1 align=center> Ana Beatriz Abreu e Giovana Vitoria </h1>

<h1><center>INTRODUÇÃO</center></h1>

As permissões foram criadas para garantir a segurança do usuário e evitar que aplicativos maliciosos tivessem acesso fácil a sensores com potencial de colocar informações pessoais em perigo, a localização, um dos sensores mais utilizados é um ótimo exemplo da razão pelo qual é essencial que existam permissões, já que a facilidade de acesso a uma informação com esse grau de sigilo poderia resultar em diversos problemas.
Este trabalho, além de ter o objetivo de ressaltar essa importância, também tem a finalidade de apresentar as principais permissões e sensores disponíveis para Android, além dos tipos de retorno para cada sensor e lista das Actions utilizadas para cada permissão.

<h2>OQUE É PERMISSÕES?</h2>

Permissões autorizam a aplicaçao a obter dados e informaçoes do usuário, além de permitir que programas tenham acesso a partes especificas do hardware do dispositivo, como sensores que fornecem localização, movimentação, entre outras funcionalidades que serão explicadas ao decorrer do trabalho.

<h3>CATEGORIAS DAS PERMISSÕES:</h3>

1.1
Permissões normais:
Consiste em a intalaçao acessar dados que vão alem do sandbox apresentamdo pouco risco a privacidade.

1.2
Permissões da instalação:
Consiste em a instalaçao obter acesso limitado a dados restritos ou execute açoes restritas, que afetam minimamente os outros aplicativos.

1.3
Permissões de assinatura:
Consiste no sistema do celular dar uma permissao a um aplicativo se ele for pertencente ao mesmo fabricante do aplicativo ou sistema operacional.

1.4
Permissões de execução:
Consiste em a intalação  acessar dados restritos que afetaram o sistema significativamente e outros apps.

1.5
Permissões especiais:
Consiste em uma permissao que so pode ser dada pelo fabricante original do sistema operacional.

<h3>PRINCIPAIS PERMISSÕES PADRÕES:</h3>

````
ACCESS_FINE_LOCATION - Permite que a aplicação mostre o localização exata com base nos provedores de local disponivel.
````
````
CAMERA - Permite que a aplicação tenha acesse a sua camera.
````
````
WRITE_EXTERNAL_STORAGE - Serve para todas as versoes do android, permite acesso de gravação a tudo o que o SDK chama de armazenamento externo 
````
````
MANAGE_EXTERNAL_STORAGE - Somente para android superior ao 11, permite acesso de gravação a quase tudo o que o SDK chama de armazenamento externo, fará com que sua aplicação seja banida de distribuidoras (Play Store ou App Store) ao menos que uma justificativa para esa permissao 
````
````
READ_CONTACTS - Permite que a aplicação tenha acesso aos seus contatos, mostrando por exemplo quem ultiliza o meus aplicativo.
````
````
CALL_PHONE - Permite que a aplicação reconheça um numero de telefone e te direcione para o aplicativo telefone para fazer uma ligação.
````
<h3> USO EM INTENTS IMPLICITAS PRINCIPAIS: </h3>

````
ACTION_VIEW - É uma intent aonde é usada para abrir/exibir dados, geralmente usada para abrir uma url.
````
````
ACTION_SEND - É uma intent usada prar compartilhar dados com outras aplicações, como mandar uma mensagem ou arquivos para outros aplicativos.
````
````
ACTION_PICK - É uma intent usada para ações ou operações específicas num contexto determinado.
````
````
ACTION_CALL - É uma intent que permite te fazer uma ligação do numero colocado na intent.
````
````
ACTION_PLAY - É uma intent que permite a reprodução da midia enviada.
````
<h2>O QUE SÃO SENSORES?</h2>

Sensores são recursos de um dispositivo que detectam tipos de estímulos específicos e retornam um resultado que pode ou não desencadear uma ação a depender do tipo de estímulo e se o programa que solicitou o sensor determinou uma consequência ou apenas a visualização.

<h3>CATEGORIAS DE SENSORES:</h3>

Os sensores compatíveis com Android são divididos em 3 categorias principais sendo elas:

1.1
Sensores de movimento – Esses sensores monitoram diversos tipos de movimento como rotação, giro, inclinação e vibração por meio de um acelerômetro ou giroscópio, a disponibilidade desse sensor depende muito do tipo de dispositivo, uma das utilizações mais comuns é a “navegação por gestos” muito utilizada pela empresa fabricadora de celulares Motorola, que liga a lanterna ao movimentar rapidamente o smartphone 2 vezes, essa detecção é feita usando o giroscópio.
Esses sensores retornam dados tipo float, o acelerômetro retorna os dados de força da aceleração e o giroscópio dados da rotação, ambos dos 3 eixos x, y e z.

1.2
Sensores ambientais – Esses sensores monitoram diversos atributos externos do ambiente ao qual o dispositivo se encontra no momento como temperatura, umidade, pressão do ar e iluminação por meio de termômetros, barômetros(pressão do ar), higrômetro(umidade do ar) e fotômetros(iluminação). É importante ressaltar que todos esses sensores de ambiente dependem do hardware, então diferente dos de movimento que tem variação entre sensores com base em software ou hardware, esse depende exclusivamente do hardware para funcionar e é importante checar se o fabricante integrou o recurso necessário antes de utilizar. Praticamente todos os dispositivos Android possuem o termômetro, mas o barômetro é um pouco mais raro e depende do fabricante, geração, finalidade e diversos outros fatores.

Esses sensores retornam um único valor diferente dos de movimento que retornam um array float com 3 valores. Por exemplo, o termômetro retorna apenas a temperatura em graus Celsius, o barômetro retorna a pressão em hPa(hectopascal, pressão atmosférica padrão ao nível médio do mar), o higrômetro retornam a umidade em porcentagem(%) e fotômetro que retorna a taxa de luminosidade em lx(quantidade de luz por metro quadrado).

1.3
Sensores de posição – Esses sensores monitoram a posição física do dispositivo, o Android oferece dois sensores para essa categoria sendo eles: sensor de campo geomagnético e o acelerômetro, também utilizado nos de movimento como citado anteriormente. Assim como os sensores ambientais, os de posição são baseados no hardware, a diferença é que a maioria dos fabricantes inclui os 2 sensores já que são usados para finalidades básicas que existem desde o começo da utilização dos smartphones, tablets e dispositivos Android no geral. Um exemplo de utilização comum desse sensor é o desligamento automático da tela ao executar ligações e direcionar o dispositivo ao ouvido ou até mesmo o recurso adiciona recentemente de manter o celular desbloqueado quando estiver no bolso, os dois exemplos para determinar a proximidade do dispositivo utilizam esses sensores.

Como explicado no 1.1, o acelerômetro retorna dados tipo float para a força da aceleração e o sensor de campo geomagnético também retorna dados dos 3 eixos, x, y e z, mas em referência a intensidade da proximidade do dispositivo em comparação a um campo magnético, no caso do exemplo das ligações eletrônicas, a pessoa.

<h3>SENSORES DE MOVIMENTO:</h3>

````
TYPE_ACCELEROMETER baseado em hardware, utiliza o acelerômetro, retornando a força da aceleração nos 3 eixos incluindo a força da gravidade. Comumente utilizado para detectar movimentos de rotação, giro, inclinação e vibração.
````
````
TYPE_GYROSCOPE baseado em hardware, utiliza o giroscópio, retornando a taxa de rotação do dispositivo em rad/s(radiano por segundo, divisão entre o deslocamente do dispositivo pelo raio da circunferência da rotação) nos 3 eixos. Muito utilizado na “navegação por gestos” dos dispositivos em ações como rotacionar o dispositivo para abrir a câmera.
````
````
TYPE_GRAVITY baseado em software ou hardware, utiliza o giroscópio, retornando a força da gravidade nos 3 eixos, detecta a agitação, inclinação, rotação. Também utilizado na “navegação por gestos”.
````
````
TYPE_LINEAR_ACCELERATION baseado em software ou hardware, utiliza o acelerômetro, retornando a força da aceleração em um único eixo excluindo a força da gravidade.
````
````
TYPE_ROTATION_VECTOR baseado em software ou hardware, utiliza o giroscópio, retornado a rotação do dispositivo nos 3 eixos em forma de vetor.
````

<h3>SENSORES AMBIENTAIS:</h3>

````
TYPE_AMBIENT_TEMPERATURE baseado em hardware, utiliza o termômetro, retornando a temperatura do ambiente em graus Celsius.
````
````
TYPE_LIGHT baseado em hardware, utiliza o fotômetro, retornando o nivel d eluz do ambiente em lx(quantidade de luz por metro quadrado), detecta e controla o brilho da tela, utilizado em recursos como “moto noturno” que diminui o brilho a depender da luz ambiente.
````
````
TYPE_PRESSURE baseado em hardware, utiliza o barômetro, retornando a pressão do ar em hPa(hectopascal, pressão atmosférica padrão ao nível médio do mar).
````
````
TYPE_RELATIVE_HUMIDITY baseado em hardware, mede a umidade relativa do ar em porcentagem, detecta o ponto de condensação, umidade absoluta e relativa.
````
````
TYPE_TEMPERATURE baseado em hardware, utiliza o termômetro, retornando a temperatura da CPU do dispositivo em graus Celsius. Importante ressaltar que esse sensor foi substituído pelo TYPE_AMBIENT_TEMPERATURE no API 14 do Android.
````
<h3>SENSORES DE POSIÇÃO:</h3>

````
TYPE_MAGNETIC_FIELD baseado em hardware, utiliza o sensor de campo geomagnético para medir o campo geomagnético do ambiente nos 3 eixos e criar uma bussola. Retorna o valor em μT(micro-Tesla), unidade de medida utilizada para densidade de fluxo magnético.
````
````
TYPE_ORIENTATION baseado em software, mede os graus de rotação nos 3 eixos e determina a posição do dispositivo. Foi depreciado na versão Android 2.2 e o tipo foi descontinuado no Android 4.4. Atualmente, esse sensor pode ser obtido por meio de uma combinação do sensor TYPE_MAGNETIC_FIELD e TYPE_ACCELEROMETER.
````
````
TYPE_PROXIMITY baseado em hardware, utiliza o sensor de campo geomagnético, mede a proximidade da tela do dispositivo em comparação a um campo magnético, objeto. Esse sensor é comumente utilizado para detectar se o smartphone está próximo ao ouvido de uma pessoa durante uma ligação e a deligar a tela.

````

<H2>CONCLUSÃO</H2>

Neste trabalho foi apresentado a importância das permissões para utilização dos sensores compatíveis com Android, mas o principal objetivo foi listar e explicar a finalidade de cada tipo de permissão e sensor, além de exemplificar com usos cotidianos que se tornaram tão comuns que podem passar despercebido.
Outra conclusão essencial que pode ser tirada dessa pesquisa foi o quão útil a criação e utilização desses sensores se tornou para os dispositivos, já que atualmente grande parte das ações que passaram do físico para o digital com o proposito de aumentar a eficiência e facilidade dependem desses sensores. Um grande exemplo disso é o aplicativo Google Maps ou qualquer outro programa que utilize o sensor de campo geomagnético, giroscópio e acelerômetro para determinar a localização, direção e movimentação do dispositivo em comparação ao ambiente, assim podendo guiar o usuário a uma rota especifica baseada na replica digital do mapa real dos lugares. Além da popular “Navegação por Gestos” citada diversas vezes como exemplo prático dos sensores ao decorrer do trabalho, mesmo que existam falhas nessa tecnologia ou ela possa não ser tão útil quanto a localização, é interessante observar a variedade de funcionalidades que os sensores podem desempenhar.


BIBLIOGRAFIA
https://developer.android.com/guide/topics/sensors/sensors_overview?hl=pt-br
https://developer.android.com/training/permissions/requesting?hl=pt-br
https://developer.android.com/guide/topics/permissions/overview?hl=pt-br
https://developer.android.com/guide/topics/sensors?hl=pt-br
https://developers.google.com/maps/documentation/android-sdk/location?hl=pt-br
https://www.androidpro.com.br/blog/armazenamento-de-dados/armazenar-dados-de-aplicativos-localmente/
https://stackoverflow.com/questions/73909410/manage-external-storage-vs-write-external-storage
https://developer.android.com/reference/android/content/Intent
