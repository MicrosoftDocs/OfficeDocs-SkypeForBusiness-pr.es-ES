---
title: Planificar la aplicación de grupo de respuesta en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: Planificación de grupos de respuesta en Skype para Telefonía IP empresarial de Business Server, que le permite configurar el enrutamiento de llamadas a grupos de usuarios. Incluye requisitos para los archivos de audio.
ms.openlocfilehash: dd98ded5af55e39f773b4a0167428ba1644cee87
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2018
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server-2015"></a>Planificar la aplicación de grupo de respuesta en Skype Empresarial Server 2015
 
Planificación de grupos de respuesta en Skype para Telefonía IP empresarial de Business Server, que le permite configurar el enrutamiento de llamadas a grupos de usuarios. Incluye requisitos para los archivos de audio.
  
Si su organización tiene grupos de personas que responda y gestión ciertos tipos de llamadas, como para servicio al cliente, un departamento de soporte interno o asistencia telefónica general para un departamento, puede implementar la aplicación de grupo de respuesta para administrar estos tipos de llamadas. El grupo de respuesta aplicación dirige y pone en cola las llamadas entrantes designa las personas, que se conocen como agentes. Puedes aumentar el uso de los servicios de asistencia telefónica y reducir la sobrecarga de ejecutar dichos servicios con un grupo de respuesta.
  
Cuando el autor de una llamada llama a un grupo de respuesta, la llamada se redirige a un agente de acuerdo con un grupo de extensiones o las respuestas del autor de la llamada frente a las preguntas de la respuesta interactiva de voz (IVR). La aplicación de grupo de respuesta utiliza métodos de enrutamiento de grupo de respuesta estándar para enrutar la llamada al siguiente agente disponible. Los métodos de enrutamiento de llamadas compatibles incluyen enrutamiento serial, según agente libre por más tiempo, paralelo, round robin y de operador (es decir, se llaman a todos los agentes al mismo tiempo para cada llamada entrante, independientemente de los estados de presencia). 
  
Si no hay ningún agente disponible, la llamada se mantiene en una cola hasta que haya alguno. Mientras se encuentra en la cola, el autor de la llamada escucha música hasta que un agente disponible acepte la llamada. Si la cola está llena o si la llamada supera el tiempo de espera mientras se encuentra en la cola, el autor de la llamada oirá un mensaje y, luego, se desconectará la llamada o se transferirá a un destino diferente, como a un correo de voz o a un número de teléfono distinto. Cuando un agente acepta la llamada, el autor de la llamada puede ver o no la identidad del agente, en función de cómo haya configurado el administrador el grupo de respuesta. Los agentes pueden ser formales, lo que significa que necesitan iniciar sesión en el grupo para poder aceptar las llamadas redirigidas al grupo, o bien informales, lo que significa que no es necesario que inicien sesión y finalicen sesión en el grupo para aceptar llamadas.
  
> [!NOTE]
> Solo los usuarios locales pueden ser agentes. Si un agente se mueve desde locales Online, llamadas de grupo de respuesta no se enrutarán a ese agente. 
  
> [!NOTE]
> La aplicación de grupo de respuesta utiliza un servicio interno, llamado haciendo coincidir, poner en cola las llamadas y buscar a agentes disponibles. Cada equipo que ejecuta la aplicación de grupo de respuesta ejecuta el servicio que hace coincidir, pero sólo un servicio que hace coincidir por grupo está activo en un momento, los demás son pasivos. Si el servicio de contactos activo deja de estar disponible durante una interrupción no planificada, se activará uno de los servicios de contactos pasivos. La aplicación de grupo de respuesta hace todo lo posible para asegurarse de que ese enrutamiento de llamadas y Queue Server continúa sin interrupciones. Pero, cuando se produce la transición del servicio de contactos, todas las llamadas que se están transfiriendo en ese momento se pierden. Por ejemplo, si la transición se debe el servidor Front-End que deje de funcionar, cualquier llamada que esté controlando el servicio activo que hace coincidir en servidor Front-End también se pierden. 
  
## <a name="response-group-workflows"></a>Flujos de trabajo de grupo de respuesta

Un flujo de trabajo define el comportamiento de una llamada desde el momento en que suena el teléfono hasta que alguien la atiende. El flujo de trabajo especifica la cola que se va a usar para poner la llamada en espera, así como el método de enrutamiento que se va a usar en grupos de extensiones o las preguntas y respuestas que se van a utilizar en grupos de respuesta interactivos. Un flujo de trabajo también define configuraciones como el mensaje de bienvenida, la música en espera, horario laboral y los días festivos.
  
> [!NOTE]
> Debe crear grupos de agentes y colas antes de crear un flujo de trabajo que use dichos elementos. 
  
## <a name="management-of-response-groups"></a>Administración de los grupos de respuesta

En Skype para Business Server, existen dos funciones de administración para administrar grupos de respuesta: respuesta grupo Administrador y Administrador de grupo de respuesta. Los administradores de grupos de respuesta pueden administrar cualquier aspecto de cualquier grupo de respuesta. Los jefes de grupo de respuesta pueden administrar sólo determinados aspectos, y sólo para los grupos de la respuesta les pertenecen. El rol de administrador puede ayudar a reducir los costos de administración, ya que puede delegar la responsabilidad limitada para grupos específicos de respuesta a cualquier usuario que está habilitada para la Telefonía IP empresarial. Tenga en cuenta que un usuario puede ser un administrador de grupos de respuesta y un administrador de grupo de respuesta. 
  
Para adaptarse a la función Manager, aplicación de grupo de respuesta utiliza un **Tipo de flujo de trabajo** administrado o no administrado. En la tabla siguiente se describen los grupos de respuesta administrados y no administrados.
  
**Grupos de respuesta administrados y no administrados**

|**Tipo de grupo de respuesta**|**Descripción**|
|:-----|:-----|
|No administrado  <br/> | Los grupos de respuesta no administrados no tienen ningún director asignado. Sólo el administrador del grupo de respuesta puede configurar estos grupos de respuesta. <br/>  Varios grupos de respuesta no administrados pueden compartir un grupo de agentes o una cola. <br/>  Al migrar grupos de respuesta desde una versión anterior a Skype para Business Server, el tipo se establece en no administrado. <br/> |
|Administrado  <br/> | Los administradores de grupos de respuesta pueden configurar cualquier aspecto de grupos de respuesta administrado. <br/>  Los jefes de grupo de respuesta no pueden ver o modificar los grupos de respuesta que no se asignan explícitamente a ellos. <br/>  Los jefes de grupo de respuesta pueden configurar sólo algunas configuraciones para los grupos de respuesta que tienen asignados explícitamente. <br/>  Los grupos de respuesta administrados no pueden compartir grupos de agentes ni colas con otros grupos de respuesta, ya sean administrados o no administrados. <br/> |
   
En la tabla siguiente se describe las acciones que los jefes de grupo de respuesta puede y no se puede realizar para los grupos de respuesta asignados a ellos.
  
**Funciones de administrador de grupo de respuesta**

|**Puede configurar:**|**Puede crear, eliminar o configurar:**|**No se puede:**|
|:-----|:-----|:-----|
| Agentes <br/>  Mensajes de bienvenida <br/>  Nombre del grupo de respuesta <br/>  Descripción <br/>  Número para mostrar <br/>  Horario comercial <br/>  Música en espera <br/>  Estado (activo/inactivo) <br/>  Flujos de trabajo del grupo de extensiones o flujos de trabajo de la respuesta interactiva de voz (IVR) <br/> | Grupos de agentes <br/>  Colas <br/>  Conjuntos de vacaciones <br/> | Crear o eliminar ningún tipo de flujo de trabajo <br/>  Modificar la configuración principal de los grupos de respuesta, como el **URI de SIP**, el **número de teléfono** o el **tipo de flujo de trabajo**.  <br/> |
   
Los jefes de grupo de respuesta pueden utilizar las siguientes herramientas para gestionar sus grupos de respuesta designado. 
  
- Panel de control de Skype Empresarial Server
    
    > [!NOTE]
    > Los jefes de grupo de respuesta sólo pueden administrar la configuración de grupo de respuesta con esta herramienta. Otro Skype para la configuración del servidor de negocios no están disponibles para los administradores. 
  
- Herramienta de configuración de grupo de respuesta
    
- Shell de administración de Skype Empresarial Server
    
Escalas de grupo de respuesta a departamentos o entornos de grupo de trabajo (para obtener más información, vea [Planear la capacidad de respuesta de grupo](http://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)) y se pueden implementar en las instalaciones de telefonía totalmente nuevo. Es compatible con las llamadas entrantes de la implementación de Telefonía IP empresarial y de la red de transporte local. Agentes pueden usar Skype para negocios, 2013 Lync, Lync 2010, Lync 2010 Attendant o Lync Phone Edition para tomar las llamadas que se dirijan a ellos.
  
## <a name="deployment-and-requirements"></a>Requisitos e implementación

La aplicación de grupo de respuesta se habilita automáticamente al implementar la Telefonía IP empresarial.
  
### <a name="hardware-and-software-requirements"></a>Requisitos de hardware y software

La aplicación de grupo de respuesta tiene los mismos requisitos de hardware, requisitos del sistema operativo y requisitos previos de software como servidores frontales. 
  
Si utiliza archivos Windows Media Audio (.wma) para anuncios y música de grupo de respuesta, todos los servidores frontales o ediciones estándar servidores que ejecutan la aplicación de grupo de respuesta deben tener Windows Media Format Runtime instalado para servidores Windows Server 2008 R2 o Microsoft Media Foundation para servidores que ejecutan Windows Server 2012 o R2 de Windows Server 2012. Para Windows Server 2008 R2, Windows Media Format Runtime se instala como parte de la experiencia de escritorio de Windows.
  
Grupo de respuesta usa **paquetes de idioma** para admitir el reconocimiento de voz y texto a voz. Estas tecnologías de voz se utilizan al configurar mensajes, como el mensaje de bienvenida y otras indicaciones, voz interactiva (IVR) de respuesta preguntas y respuestas. De forma predeterminada, los 26 admiten language packs se instalan al implementar Skype para Business Server.
  
### <a name="port-requirements"></a>Requisitos de los puertos

La aplicación de grupo de respuesta utiliza los siguientes puertos:
  
- **5071 de puerto** para solicitudes de escucha de SIP
    
- **8404 de puerto** para las comunicaciones
    
    > [!NOTE]
    > Este puerto se utiliza para el servicio que hace coincidir y es necesario cuando se implementa la aplicación de grupo de respuesta en un grupo que tiene más de un servidor de Front-End. 
  
   > [!NOTE]
   > Estos puertos son valores predeterminados que se pueden cambiar mediante el cmdlet **Set-CsApplicationServer** . Para obtener más información acerca de este cmdlet, vea el Skype para la documentación del Shell de administración de servidor empresarial.
  
### <a name="audio-file-requirements"></a>Requisitos de archivos de audio

El formato de archivo de onda (.wav) de grupo de respuesta aplicación admite y un archivo de Windows Media audio (.wma) formato para mensajes de grupo de respuesta, música en espera o preguntas de voz interactiva (IVR) de la respuesta.
  
El formato de archivo de audio de Windows Media requiere que esté instalado Windows Media Format Runtime en servidores frontales ejecuta Windows Server 2008 R2 y Windows Server 2008. Para obtener más información, mira "Requisitos de software" anteriormente en esta sección.
  
#### <a name="supported-wave-file-formats"></a>Formatos de archivo wave compatibles

Todos los archivos wave necesitan cumplir los requisitos siguientes:
  
- Archivo de 8 bits o de 16 bits
    
- Formato de modulación lineal por impulsos codificados (LPCM), A-Law o mu-Law
    
- Mono o estéreo
    
- 4 MB o menos
    
Para obtener el máximo rendimiento de los archivos wave, recomendamos usar un archivo wave mono de 16 bits a 16 kHz. 
  
#### <a name="supported-windows-media-audio-file-formats"></a>Formatos de archivo de audio de Windows Media compatibles

Si usas un archivo de audio de Windows Media, considera la posibilidad de usar velocidades de bits lentas y comprueba el rendimiento del sistema cuando se somete a carga.
  
Puedes usar Microsoft Expression Encoder 4 para convertir un archivo al formato de audio de Windows Media. Para descargar el 4 de Expression Encoder, consulte [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843).
  
### <a name="response-group-configuration-tool-requirements"></a>Requisitos para la herramienta de configuración del grupo de respuesta

La herramienta de configuración de grupo de respuesta admite las combinaciones de sistemas operativos y exploradores web que se describe en la tabla siguiente.
  
> [!NOTE]
> Se admiten las versiones de 32 y 64 bits de los sistemas operativos. Solamente se admiten las versiones de 32 bits de Internet Explorer. 
  
**Sistemas operativos y exploradores Web**

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
  
**Sistemas operativos y exploradores Web**

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
  
- Skype para el cliente de escritorio de negocios
    
- Cliente de escritorio Lync 2013
    
- Cliente de escritorio Lync 2010
    
- Operador de Lync 2010
    
- Office Communications Server 2007 R2 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> La aplicación de grupo de respuesta no es compatible con clientes móviles de Lync. 
  
El cliente específico que puede utilizar depende del tipo de usuario del grupo de respuesta que está: 
  
- Los **autores de llamadas** pueden llamar a un grupo de respuesta a través de cualquiera de los clientes de la lista anterior y a través de un teléfono estándar por la red telefónica conmutada (RTC).
    
- **Agentes informales** (los agentes que no firman dentro y fuera de sus grupos para aceptar llamadas) pueden aceptar llamadas usando el operador, Lync o Lync Phone Edition. Agentes informales están firmados automáticamente en sus grupos cuando inician sesión en Skype para Business Server mediante uno de estos clientes.
    
- **Agentes formales** (los agentes que deben firmar dentro y fuera de sus grupos para aceptar llamadas) pueden aceptar llamadas mediante Skype para el negocio y acceso a la consola de agente desde el elemento de menú o mediante el operador y acceso a la consola de agente directamente desde Internet Explorer.
    
## <a name="capacity-planning"></a>Planificación de la capacidad

En la tabla siguiente se describe el modelo de usuario de grupo de respuesta que se puede utilizar como base para los requerimientos de planificación de capacidad.
  
> [!NOTE]
> En las cantidades de la tabla siguiente se presupone que usas archivos wave (.wav) mono de 16 bits a 16 kHz para todos los archivos de audio del grupo de respuesta. Si usas otros formatos de archivo, como audio de Windows Media (.wma), las cantidades pueden variar. 
  
> [!IMPORTANT]
> Ten en cuenta que, para planificar la capacidad de la recuperación ante desastres, cada grupo de un grupo emparejado necesita poder gestionar las cargas de trabajo para todos los grupos de respuesta en ambos grupos. 
  
**Modelo de grupo de respuesta de usuario**

|**Métrica**|**Por cada grupo de servidores Enterprise Edition <br/> (con 8 servidores frontales)**|**Por cada servidor Standard Edition**|
|:-----|:-----|:-----|
|Llamadas entrantes por segundo  <br/> |16  <br/> |2  <br/> |
|Llamadas simultáneas conectadas a IVR o a la música en espera  <br/> |480  <br/> |60  <br/> |
|Sesiones anónimas simultáneas (sin MI)  <br/> |224  <br/> |28  <br/> |
|Sesiones anónimas simultáneas (con MI)  <br/> |64  <br/> |8  <br/> |
|Agentes activos (formales e informales)  <br/> |2400  <br/> |2400  <br/> |
|Cantidad de grupos de extensiones  <br/> |800  <br/> |800  <br/> |
|Cantidad de grupos de IVR (uso del reconocimiento de voz)  <br/> |400  <br/> |400  <br/> |
   

