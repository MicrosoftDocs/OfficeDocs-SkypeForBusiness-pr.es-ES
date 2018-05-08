---
title: Planificar la aplicación de grupo de respuesta en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: Planeación de grupos de respuesta en Skype para Business Server Enterprise Voice, que le permite configurar el enrutamiento de llamadas a grupos de usuarios. Incluye requisitos para los archivos de audio.
ms.openlocfilehash: 628126cfc3815dfabdf0e73c962e8dcff326b416
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server-2015"></a>Planificar la aplicación de grupo de respuesta en Skype Empresarial Server 2015
 
Planeación de grupos de respuesta en Skype para Business Server Enterprise Voice, que le permite configurar el enrutamiento de llamadas a grupos de usuarios. Incluye requisitos para los archivos de audio.
  
Si su organización tiene grupos de personas que responder y gestionar ciertos tipos de llamadas, como para servicio al cliente, una asistencia interno o soporte técnico de teléfono general para un departamento, puede implementar la aplicación de grupo de respuesta para administrar estos tipos de llamadas. El grupo de respuesta aplicación enruta y pone en cola las llamadas entrantes a designar las personas, que se conocen como agentes. Puedes aumentar el uso de los servicios de asistencia telefónica y reducir la sobrecarga de ejecutar dichos servicios con un grupo de respuesta.
  
Cuando el autor de una llamada llama a un grupo de respuesta, la llamada se redirige a un agente de acuerdo con un grupo de extensiones o las respuestas del autor de la llamada frente a las preguntas de la respuesta interactiva de voz (IVR). La aplicación de grupo de respuesta usa los métodos de enrutamiento de grupo de respuesta estándar para enrutar la llamada al siguiente agente disponible. Los métodos de enrutamiento de llamadas compatibles incluyen enrutamiento serial, según agente libre por más tiempo, paralelo, round robin y de operador (es decir, se llaman a todos los agentes al mismo tiempo para cada llamada entrante, independientemente de los estados de presencia). 
  
Si no hay ningún agente disponible, la llamada se mantiene en una cola hasta que haya alguno. Mientras se encuentra en la cola, el autor de la llamada escucha música hasta que un agente disponible acepte la llamada. Si la cola está llena o si la llamada supera el tiempo de espera mientras se encuentra en la cola, el autor de la llamada oirá un mensaje y, luego, se desconectará la llamada o se transferirá a un destino diferente, como a un correo de voz o a un número de teléfono distinto. Cuando un agente acepta la llamada, el autor de la llamada puede ver o no la identidad del agente, en función de cómo haya configurado el administrador el grupo de respuesta. Los agentes pueden ser formales, lo que significa que necesitan iniciar sesión en el grupo para poder aceptar las llamadas redirigidas al grupo, o bien informales, lo que significa que no es necesario que inicien sesión y finalicen sesión en el grupo para aceptar llamadas.
  
> [!NOTE]
> Solo los usuarios locales pueden ser agentes. Si un agente se mueve de local a en línea, las llamadas de grupo de respuesta no se enrutarán a ese agente. 
  
> [!NOTE]
> La aplicación de grupo de respuesta usa un servicio interno, llamado correspondencia, poner en cola las llamadas y buscar a los agentes disponibles. Cada equipo que ejecuta la aplicación de grupo de respuesta ejecuta el servicio de correspondencia, pero solo un servicio de correspondencia por grupo de servidores está activo en un momento--los demás son pasivos. Si el servicio de contactos activo deja de estar disponible durante una interrupción no planificada, se activará uno de los servicios de contactos pasivos. La aplicación de grupo de respuesta no la mejor manera para asegurarse de que el enrutamiento de llamadas y puesta en cola continúen sin interrupciones. Pero, cuando se produce la transición del servicio de contactos, todas las llamadas que se están transfiriendo en ese momento se pierden. Por ejemplo, si la transición es debido al servidor Front-End que deje de funcionar, las llamadas atendidas actualmente por el servicio de correspondencia activo en el también se pierden servidor Front-End. 
  
## <a name="response-group-workflows"></a>Flujos de trabajo de grupo de respuesta

Un flujo de trabajo define el comportamiento de una llamada desde el momento en que suena el teléfono hasta que alguien la atiende. El flujo de trabajo especifica la cola que se va a usar para poner la llamada en espera, así como el método de enrutamiento que se va a usar en grupos de extensiones o las preguntas y respuestas que se van a utilizar en grupos de respuesta interactivos. Un flujo de trabajo también define configuraciones como el mensaje de bienvenida, la música en espera, horario laboral y los días festivos.
  
> [!NOTE]
> Debe crear grupos de agentes y colas antes de crear un flujo de trabajo que use dichos elementos. 
  
## <a name="management-of-response-groups"></a>Administración de los grupos de respuesta

En Skype para Business Server, dos roles de administración están disponibles para la administración de grupos de respuesta: Director de grupo de respuesta y Administrador de grupo de respuesta. Los administradores de grupo de respuesta pueden administrar todos los aspectos de cualquier grupo de respuesta. Administradores del grupo de respuesta pueden administrar sólo determinados aspectos, y solo para grupos de la respuesta son propietarios. La función Administrador puede ayudar a reducir los costos de administración, ya que puede delegar responsabilidades limitadas para grupos de respuesta específicos a cualquier usuario habilitado para Enterprise Voice. Tenga en cuenta que un usuario puede ser un administrador de grupos de respuesta y un administrador de grupo de respuesta. 
  
Para dar cabida a la función de administrador, la aplicación de grupo de respuesta utiliza un **Tipo de flujo de trabajo** de administrado o no administrado. En la tabla siguiente se describen los grupos de respuesta administrados y no administrados.
  
**Grupos de respuesta administrados y no administrados**

|**Tipo de grupo de respuesta**|**Descripción**|
|:-----|:-----|
|No administrado  <br/> | Los grupos de respuesta no administrados no tienen ningún director asignado. Sólo el Administrador de grupos de respuesta puede configurar estos grupos de respuesta. <br/>  Varios grupos de respuesta no administrados pueden compartir un grupo de agentes o una cola. <br/>  Cuando se migran grupos de respuesta desde una versión anterior a Skype para Business Server, el tipo se establece como no administrados. <br/> |
|Administrado  <br/> | Los administradores de grupo de respuesta pueden configurar cualquier aspecto de los grupos de respuesta administrados. <br/>  Los administradores de grupo de respuesta no se pueden ver o modificar los grupos de respuesta que no se haya asignado explícitamente a ellos. <br/>  Los administradores de grupo de respuesta pueden configurar solo algunas opciones de configuración para los grupos de respuesta que se les haya asignado explícitamente. <br/>  Los grupos de respuesta administrados no pueden compartir grupos de agentes ni colas con otros grupos de respuesta, ya sean administrados o no administrados. <br/> |
   
En la siguiente tabla se describe las acciones que los administradores del grupo de respuesta puede y no se puede realizar para los grupos de respuesta asignados a ellos.
  
**Capacidades de director de grupo de respuesta**

|**Puede configurar:**|**Puede crear, eliminar o configurar:**|**No se puede:**|
|:-----|:-----|:-----|
| Agentes <br/>  Mensajes de bienvenida <br/>  Nombre de grupo de respuesta <br/>  Descripción <br/>  Número para mostrar <br/>  Horario comercial <br/>  Música en espera <br/>  Estado (activo/inactivo) <br/>  Flujos de trabajo del grupo de extensiones o flujos de trabajo de la respuesta interactiva de voz (IVR) <br/> | Grupos de agentes <br/>  Colas <br/>  Conjuntos de vacaciones <br/> | Crear o eliminar ningún tipo de flujo de trabajo <br/>  Modificar la configuración principal de los grupos de respuesta, como el **URI de SIP**, el **número de teléfono** o el **tipo de flujo de trabajo**.  <br/> |
   
Los administradores de grupo de respuesta pueden usar las siguientes herramientas para administrar sus grupos de respuesta designado. 
  
- Panel de control de Skype Empresarial Server
    
    > [!NOTE]
    > Los administradores de grupo de respuesta sólo pueden administrar la configuración de grupo de respuesta con esta herramienta. Otro Skype para la configuración de Business Server no están disponibles para los administradores. 
  
- Herramienta de configuración de grupo de respuesta
    
- Shell de administración de Skype Empresarial Server
    
Escala de grupo de respuesta también a departamentos o entornos de grupo de trabajo (para obtener información detallada, vea [Planear la capacidad de grupo de respuesta](http://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)) y se pueden implementar en instalaciones de telefonía totalmente nuevas. Es compatible con las llamadas entrantes de la implementación de Enterprise Voice y de la red del operador local. Agentes pueden utilizar Skype para profesionales, Lync 2013, Lync 2010, Lync 2010 Attendant o Lync Phone Edition para atender las llamadas enrutadas a ellos.
  
## <a name="deployment-and-requirements"></a>Requisitos e implementación

La aplicación de grupo de respuesta se habilita automáticamente al implementar Enterprise Voice.
  
### <a name="hardware-and-software-requirements"></a>Requisitos de hardware y software

La aplicación de grupo de respuesta tiene los mismos requisitos de hardware, requisitos del sistema operativo y requisitos previos de software como servidores Front-End. 
  
Si utiliza archivos de Windows Media Audio (.wma) para anuncios y música de grupo de respuesta, todos los servidores Front-End o las ediciones Standard servidores que ejecutan la aplicación de grupo de respuesta deben tener instalado para los servidores que ejecutan Windows Windows Media Format Runtime Server 2008 R2 o Microsoft Media Foundation para los servidores que ejecutan Windows Server 2012 o Windows Server 2012 R2. Para Windows Server 2008 R2, el tiempo de ejecución de Windows Media Format se instala como parte de la experiencia de escritorio de Windows.
  
Grupo de respuesta usa **paquetes de idioma** para admitir el reconocimiento de voz y texto a voz. Estas tecnologías de voz se usan al configurar los mensajes, como el mensaje de bienvenida y otros mensajes, interactiva de voz (IVR) de respuesta preguntas y respuestas. De forma predeterminada, el 26 admite el idioma al implementar Skype para Business Server se hayan instalado los paquetes.
  
### <a name="port-requirements"></a>Requisitos de los puertos

La aplicación de grupo de respuesta utiliza los siguientes puertos:
  
- **Puerto 5071** para solicitudes de escucha SIP
    
- **Puerto 8404** para las comunicaciones
    
    > [!NOTE]
    > Este puerto se usa para el servicio de correspondencia y es necesario cuando se implementa la aplicación de grupo de respuesta en un grupo de servidores que tiene más de un servidor Front-End. 
  
   > [!NOTE]
   > Estos puertos son la configuración predeterminada que se puede cambiar mediante el cmdlet **Set-CsApplicationServer** . Para obtener más información acerca de este cmdlet, vea el Skype para la documentación del Shell de administración de servidor empresarial.
  
### <a name="audio-file-requirements"></a>Requisitos de archivos de audio

El formato de archivo de onda (.wav) de admite de aplicación de grupo de respuesta y el archivo de Windows Media audio (.wma) formato para los mensajes de grupo de respuesta, música en espera o preguntas de voz interactiva (IVR) de la respuesta.
  
El formato de archivo de audio de Windows Media requiere que el tiempo de ejecución de formato de Windows Media está instalado en los servidores Front-End que ejecutan Windows Server 2008 R2 y Windows Server 2008. Para obtener más información, mira "Requisitos de software" anteriormente en esta sección.
  
#### <a name="supported-wave-file-formats"></a>Formatos de archivo wave compatibles

Todos los archivos wave necesitan cumplir los requisitos siguientes:
  
- Archivo de 8 bits o de 16 bits
    
- Formato de modulación lineal por impulsos codificados (LPCM), A-Law o mu-Law
    
- Mono o estéreo
    
- 4 MB o menos
    
Para obtener el máximo rendimiento de los archivos wave, recomendamos usar un archivo wave mono de 16 bits a 16 kHz. 
  
#### <a name="supported-windows-media-audio-file-formats"></a>Formatos de archivo de audio de Windows Media compatibles

Si usas un archivo de audio de Windows Media, considera la posibilidad de usar velocidades de bits lentas y comprueba el rendimiento del sistema cuando se somete a carga.
  
Puedes usar Microsoft Expression Encoder 4 para convertir un archivo al formato de audio de Windows Media. Para descargar la expresión codificador 4, consulte [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843).
  
### <a name="response-group-configuration-tool-requirements"></a>Requisitos para la herramienta de configuración del grupo de respuesta

La herramienta de configuración de grupo de respuesta admite combinaciones de sistemas operativos y exploradores web que se describen en la siguiente tabla.
  
> [!NOTE]
> Se admiten las versiones de 32 y 64 bits de los sistemas operativos. Solamente se admiten las versiones de 32 bits de Internet Explorer. 
  
**Los sistemas operativos y exploradores Web**

|**Sistema operativo**|**Explorador Web**|
|:-----|:-----|
|Windows Vista con Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows 7  <br/> Windows 7 con Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2008 con Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 con Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||
   
### <a name="response-group-agent-console"></a>Consola del agente del grupo de respuesta

La consola del agente admite combinaciones de los sistemas operativos y los exploradores web que se describen en la tabla siguiente.
  
> [!NOTE]
> Se admiten las versiones de 32 y 64 bits de los sistemas operativos. Solamente se admiten las versiones de 32 bits de Internet Explorer. 
  
**Los sistemas operativos y exploradores Web**

|**Sistema operativo**|**Explorador Web**|
|:-----|:-----|
|Windows Vista con Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows 7  <br/> Windows 7 con Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2008 con Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 con Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2012  <br/> |
|Windows Server 2012 R2  <br/> |
   
## <a name="client-support"></a>Compatibilidad con clientes

La aplicación de grupo de respuesta admite a los siguientes clientes:
  
- Skype para el cliente de escritorio empresarial
    
- Cliente de escritorio de Lync 2013
    
- Cliente de escritorio de Lync 2010
    
- Operador de Lync 2010
    
- Office Communications Server 2007 R2 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> La aplicación de grupo de respuesta no se admite en clientes móviles de Lync. 
  
El cliente concreto que puede usar depende del tipo de usuario de grupo de respuesta que está: 
  
- Los **autores de llamadas** pueden llamar a un grupo de respuesta a través de cualquiera de los clientes de la lista anterior y a través de un teléfono estándar por la red telefónica conmutada (RTC).
    
- **Agentes informales** (los agentes que no conectarse y desconectarse de sus grupos para aceptar llamadas) pueden aceptar llamadas mediante el uso de Attendant, Lync o Lync Phone Edition. Agentes informales se conectan automáticamente en sus grupos cuando inician sesión Skype para Business Server mediante uno de estos clientes.
    
- **Agentes formales** (los agentes que deben conectarse y desconectarse de sus grupos para aceptar llamadas) pueden aceptar llamadas mediante Skype para la empresa y obtener acceso a la consola de agente desde el elemento de menú o mediante el operador y obtener acceso a la consola de agente directamente desde el Explorador de Internet.
    
## <a name="capacity-planning"></a>Planificación de la capacidad

En la siguiente tabla se describe el modelo de usuario de grupo de respuesta que puede usar como base para los requisitos de planeación de capacidad.
  
> [!NOTE]
> En las cantidades de la tabla siguiente se presupone que usas archivos wave (.wav) mono de 16 bits a 16 kHz para todos los archivos de audio del grupo de respuesta. Si usas otros formatos de archivo, como audio de Windows Media (.wma), las cantidades pueden variar. 
  
> [!IMPORTANT]
> Ten en cuenta que, para planificar la capacidad de la recuperación ante desastres, cada grupo de un grupo emparejado necesita poder gestionar las cargas de trabajo para todos los grupos de respuesta en ambos grupos. 
  
**Modelo de usuario de grupo de respuesta**

|**Métrica**|**Por grupo de servidores Enterprise Edition <br/> (con 8 servidores Front-End)**|**Por servidor Standard Edition**|
|:-----|:-----|:-----|
|Llamadas entrantes por segundo  <br/> |16  <br/> |2  <br/> |
|Llamadas simultáneas conectadas a IVR o a la música en espera  <br/> |480  <br/> |60  <br/> |
|Sesiones anónimas simultáneas (sin MI)  <br/> |224  <br/> |28  <br/> |
|Sesiones anónimas simultáneas (con MI)  <br/> |64  <br/> |8  <br/> |
|Agentes activos (formales e informales)  <br/> |2400  <br/> |2400  <br/> |
|Cantidad de grupos de extensiones  <br/> |800  <br/> |800  <br/> |
|Cantidad de grupos de IVR (uso del reconocimiento de voz)  <br/> |400  <br/> |400  <br/> |
   

