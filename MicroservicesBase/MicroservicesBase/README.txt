1. Instalar docker desktop 
	https://docker.com/get-started/ 
	https://hub.docker.com/
2. En cmd instalar wsl --install
3. Instalar terminal ubuntu en docker
4. Abrir docker desktop para que corra las instancias
5. Comandos de docker:
	"docker version" (muestra version y lo que esta corriendo en docker engine)
	"docker run tu-programa" local o remoto (puede ser de tus locales o del docker hub)
	"docker ps" Lista los contenedores e imagenes corriendose con sus datos
	"docker stop tu-programa" detiene una ejecucuion
	"docker create" crea un container y devuelve el id
	"docker start tu-id" inicia el container y devuelve el id
	"docker start -a tu-id" inicia el container pero devuelve los outputs en vez de la id
	"docker ps -all" lista todos los container y muestra los estados de ejecucuion
	"docker stop" lo hace finalizar y apagar el container
	"docker kill" lo mata al proceso sin precauciones
	"docker pull tu-programa" Trae una imagen del hub hacia lo local

Instalando un container con Redis para bd
1. "docker pull redis"
2. "docker run -d -p 6379:6379 --name redis_container redis"
   "docker run=ejecuta -d=imprime log -p= puertos	--name=nombre el container redis=imagen desde donde va a crear el container"
   7363575492b5a729510c6c4bd11ca0f56be34a70fdb581dd97a40aef5e68c378
3. "docker exec -it redis_container sh" Ingresa al bash de linux
4. "redis cli" ingresa al servicio de redis
5. ping PONG,para chekear la conexion
set nombre Nelson
get nombre

Instalando Rabbit en un docker
1. Instalar la imagen descargando desde el docker server online
	docker run -d --hostname rabbit-server --name rabbit-vaxi-web -p 5672:5672 -p15672:15672 rabbitmq
2. Pugins en el server de rabbit
	Entrar: docker exec -it rabbit-web bash
	Listarlos: rabbitmq-plugins list
	Activarlo: rabbitmq-plugins enable rabbitmq_management
3. Entrar a pagina de administracion de rabbit User y pass por defecto
	localhost:15672
	User: guest Pass: guest
4. Par continuar ingresamos: clear
5. Para administrar rabbit desde el cmd: rabbitmqctl
6. Para crear un user: rabbitmqctl add_user vaxidrez VaxiDrez2005
7. Asignarle un rol: rabbitmqctl set_user_tags vaxidrez administrator
8. Permisos globales: rabbitmqctl set_permissions -p / vaxidrez ".*"  ".*"  ".*"