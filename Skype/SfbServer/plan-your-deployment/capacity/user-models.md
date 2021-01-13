---
title: Modelos de usuario en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c551371c-d740-4372-bada-f0d713ec0d33
description: Los modelos de usuario que se describen aquí proporcionan la base para las medidas y recomendaciones de planeación de capacidad descritas en Planeación de capacidad del uso del modelo de usuario para Skype Empresarial Server.
ms.openlocfilehash: 65ff967c64f569d73d15de1493aa4d3667dbf7e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827610"
---
# <a name="user-models-in-skype-for-business-server"></a>Modelos de usuario en Skype Empresarial Server
 
Los modelos de usuario que se describen aquí proporcionan la base para las medidas de planeación de capacidad y las recomendaciones descritas en Planeación de capacidad de uso del modelo de usuario [para Skype Empresarial Server.](user-model.md)
  
## <a name="skype-for-business-server-user-models"></a>Modelos de usuario de Skype Empresarial Server

En la tabla siguiente se describe el modelo de usuario para el registro, los contactos, la mensajería instantánea (MI) y la presencia de Skype Empresarial Server.
  
**Modelo de usuario de registro y entorno**

|**Categoría**|**Descripción**|
|:-----|:-----|
|Tamaño de implementación y distribución  <br/> |Se modela una implementación de gran tamaño con tres sitios centrales y un grupo de servidores front-end por sitio.  <br/> |
|Porcentaje de usuarios de Active Directory  <br/> |Se supone que el 70 % de todos los usuarios de Active Directory de la organización están habilitados para Skype Empresarial Server. El 80 % de los usuarios habilitados ha iniciado sesión en Skype Empresarial Server cada día (80 % de simultaneidad). Los usuarios simultáneos constituyen la base de los cálculos del resto de esta sección.  <br/> |
|Cambios en Active Directory  <br/> |Se supone que el 0,5 % del total de usuarios se crean y habilitan para Skype Empresarial en Active Directory cada semana, y que el 0,5 % del total de usuarios se deshabilita de Active Directory y de Skype Empresarial cada semana. El 5 % de los usuarios cambia al menos un atributo de Active Directory cada semana.  <br/> |
|Grupos de distribución de Active Directory  <br/> |Se supone que el número de grupos de distribución de Active Directory de la organización es igual al triple de todos los usuarios de Active Directory. Los grupos de distribución tienen las dimensiones siguientes:  <br/> • El 64 % tiene de 2 a 30 usuarios  <br/> • El 13 % tiene de 31 a 50 usuarios  <br/> • El 10 % tiene de 51 a 100 usuarios  <br/> • El 13 % tiene de 101 a 500 usuarios  <br/> |
|Usuarios de voz sobre IP (VoIP)  <br/> |El 60 % de los usuarios de Skype Empresarial Server están habilitados para las comunicaciones unificadas (es decir, sus números de teléfono son propiedad de Skype Empresarial Server).  <br/> |
|Distribución de clientes registrados  <br/> |El 65 % de los clientes ejecutan software de Skype Empresarial, incluido Skype Empresarial y Lync Phone Edition.  <br/> El 30 % de los clientes que ejecutan software cliente desde una versión anterior de Lync.  <br/> El 5 % de los clientes que usan Skype Empresarial Web App.  <br/> Si la movilidad está habilitada, se supone que el 40 % de los usuarios usa la movilidad simultáneamente con las otras opciones de cliente registradas mencionadas anteriormente. En este caso, la relación de varios puntos de presencia (MPOP) del cliente es de 1:1,9. Si la movilidad está deshabilitada, la relación de MPOP es de 1:1,5.  <br/> |
|Distribución de usuarios remotos  <br/> |El 70 % de los usuarios se conecta internamente.  <br/> El 30 % de los usuarios que se conectan a través de un servidor perimetral (opcionalmente también puede tener un director aquí, pero no es necesario).  <br/> |
|Distribución de contactos  <br/> |El número máximo de contactos que tiene un usuario es de 1.000. Menos del 1 % de los usuarios tiene 1.000 contactos. Menos del 25 % de los usuarios tiene 100 o más contactos.  <br/> Una media de 80 contactos para los usuarios con conectividad en la nube pública. De estos usuarios:  <br/> • El 50 % de los contactos están dentro de la organización. El 10 % de estos usuarios corresponde a usuarios remotos que se conectan desde fuera del firewall.  <br/> • El 40 % de los contactos son usuarios de Skype.  <br/> • El 10 % de los contactos son de socios federados.  <br/> Una media de 50 contactos para los usuarios sin conectividad en la nube pública. De estos usuarios:  <br/> • El 80 % de los contactos están dentro de la organización. El 10 % de estos usuarios corresponde a usuarios remotos que se conectan desde fuera del firewall.  <br/> • El 20 % de los contactos son de socios federados.  <br/> Cada usuario tiene un grupo de distribución en su lista de contactos. Para las pruebas de rendimiento, se supone que los grupos de distribución son siempre expandidos.  <br/> |
|Tiempo de la sesión  <br/> |La sesión de inicio media de un usuario dura doce horas. Todos los usuarios inician sesión durante los primeros 120 minutos tras el inicio de la sesión.  <br/> |
   
**Modelo de usuario de presencia y MI**

|**Categoría**|**Descripción**|
|:-----|:-----|
|Sesiones de MI de punto a punto  <br/> |Cada usuario mantiene una media diaria de seis sesiones de MI de punto a punto.  <br/> Diez mensajes instantáneos por sesión.  <br/> Cada mensaje coincide con dos mensajes SIP INFO y 2 mensajes SIP 200 OK (para los indicadores de estado como " \<Name\> es escribir").  <br/> |
|Sesiones de mensajería instantánea de grupo  <br/> |El número medio de mensajes enviados en una sesión de solo mensajería instantánea de grupo es de 5 por usuario.  <br/> El número medio de mensajes enviados en la parte de mensajería instantánea de una conferencia antivirus es de 2 por usuario.  <br/> |
|Sondeo de presencia  <br/> |En términos generales, se supone que los sondeos de presencia tienen unos 60 sondeos de media por usuario y hora. Para cada usuario, se supone una media de:  <br/> • Un sondeo por día de la presencia de usuarios en la pestaña de organización del usuario (pero no en la lista de contactos). El número medio de no contactos en la pestaña de organización del usuario es de 15 usuarios. Dos operaciones de ver tarjetas de contacto al día.  <br/> • Un sondeo de presencia cada vez que el usuario hace clic en otro usuario para iniciar una conversación, estimado en una vez por hora.  <br/> • Seis búsquedas de usuario por hora. Cada vez que se realiza una búsqueda, se envía un sondeo por lotes para todos los usuarios de la lista de resultados de búsqueda. Se supone que el tamaño promedio de los resultados de búsqueda es 20. Si los resultados de la búsqueda permanecen en pantalla, el sondeo por lotes se actualiza cada 5 minutos; Damos por hecho que habrá dos actualizaciones por hora.  <br/> • Cuando el usuario abre u muestra una vista previa de un correo electrónico en Outlook, un sondeo de la presencia de los usuarios en los campos Para: y CC: del correo electrónico, estimado en cinco correos electrónicos por hora y cuatro usuarios por correo electrónico.  <br/> |
|Suscripciones de presencia  <br/> |Cuando un usuario agrega a otro como contacto, el primer usuario se suscribe a cinco categorías de información acerca del segundo usuario. Las actualizaciones de estas categorías de información se envían automáticamente al primer usuario. <br/> Para cada cliente, se envía una única petición de suscripción por lotes para obtener el estado de presencia de una media de 40 contactos, con 40 diálogos adicionales para obtener la presencia de los contactos federados.  <br/> La presencia de los miembros de un grupo de distribución expandido se averigua a través de las suscripciones de presencia persistente, y no a través de los sondeos, y se modela como 1 expansión por usuario durante cada 2 horas.  <br/> Las suscripciones breves se suceden cuando un usuario inicia sesión, hay una suscripción por lotes para todos los contactos del usuario y, a continuación, el usuario cierra sesión pronto. Se suponen 6 suscripciones breves por usuario y hora, y cada suscripción dura 10 minutos. <br/> |
|Publicación de presencia  <br/> |El estado de presencia se publica a una media de 4 publicaciones por usuario y hora, con un máximo de 6 por usuario y hora.  <br/> |
|Tamaño del documento de presencia  <br/> |Se supone que el tamaño medio de un documento de presencia completo es de 4 K (de 25 K como máximo).  <br/> |
   
En la tabla siguiente se describe el modelo de usuario para el uso de la libreta de direcciones.
  
**Modelo de usuario para el uso de la libreta de direcciones**

|**Modo de búsqueda de la libreta de direcciones**|**Usage**|
|:-----|:-----|
|Solo consulta web de la libreta de direcciones (todas las consultas realizadas por el servicio de consulta web de la libreta de direcciones)  <br/> |Cuatro consultas de prefijo por usuario y día.  <br/> 60 consultas de búsqueda exactas por usuario y día. El 40 % de estas consultas se procesa por lotes, con una media de 20 contactos por consulta. El 60 % restante de las consultas es para un solo contacto.  <br/> 25 consultas de fotografías por usuario y día. 24 son para una sola fotografía y la consulta restante se realiza por lotes, con una media de 20 contactos.  <br/> Una consulta de búsqueda de organización total por usuario y día.  <br/> |
|Modo mixto, se usa el archivo de la libreta de direcciones y las consultas web. Este es el modo predeterminado.  <br/> |Solo dos tipos de consultas van a la red, las consultas de fotografía y de búsqueda de organización total.  <br/> 25 consultas de fotografías por usuario y día. 24 son para una sola fotografía y la otra es una consulta por lotes con una media de 20 contactos.  <br/> Una consulta de búsqueda de organización total por usuario y día.  <br/> |
   
En la siguiente tabla se describe el modelo de conferencia.
  
**Modelo de conferencia**

|**Categoría**|**Descripción**|
|:-----|:-----|
|Reuniones programadas y reuniones de tipo "Reunirse ahora"  <br/> |60 % programadas, 40 % no programadas.  <br/> De las reuniones programadas, se supone que el 80 % se asignan a conferencias, que son repeticiones de conferencias periódicas; El 10 % son reuniones abiertas de una sola vez; El 8 % son reuniones anónimas de una sola vez y el 2 % son reuniones cerradas de una sola vez.  <br/> |
|Distribución de clientes de conferencia  <br/> |Para reuniones programadas:  <br/> • El 65 % de los usuarios de conferencia usa Skype Empresarial 2016.  <br/> • El 5 % de los usuarios de conferencia usa Skype Empresarial Web App.  <br/> • El 30 % de los usuarios de conferencia usa clientes anteriores, incluidos Lync 2013 y Microsoft Lync 2010.  <br/> Para reuniones no programadas:  <br/> • El 70 % de los usuarios de conferencia usa Skype Empresarial.  <br/> • El 30 % de los usuarios de conferencia usa clientes anteriores, incluidos Lync 2013 y Microsoft Lync 2010.  <br/> |
|Concurrencia en reuniones  <br/> |El 5 % de los usuarios asistirá a conferencias durante el horario de trabajo. Por tanto, en un grupo de 80.000 usuarios, hasta 4.000 usuarios pueden asistir a conferencias en un momento dado.  <br/> |
|Distribución de audio en las reuniones  <br/> |El 40 % combinó el audio por VoIP y la conferencia de acceso telefónico local, con una relación 3 usuarios de VoIP por 1 usuario de acceso telefónico.  <br/> El 35 % usó solo audio por VoIP.  <br/> El 15 % usó solo audioconferencia de acceso telefónico local.  <br/> El 10 % no usó audio (conferencias solo de mensajería instantánea, con una media de cinco mensajes enviados por usuario).  <br/> |
|Combinación de medios para conferencias  <br/> |El 75 % de las conferencias son conferencias web, con audio más otras modalidades de colaboración.  <br/> Para estas conferencias, los otros métodos de colaboración son los siguientes:  <br/> **Nota:** Estas cifras suman más del 100 % porque una conferencia puede tener varios métodos de colaboración. <br/> • El 50 % agrega el uso compartido de aplicaciones. Se supone que un usuario envía datos a una velocidad pico de 1,1 MB por segundo.  <br/> • El 50 % agrega mensajería instantánea (con una media de 2 mensajes por usuario).  <br/> • El 20 % agrega colaboración de datos, incluidos PowerPoint o pizarra En estos, una media de 2 archivos de PowerPoint presentados por conferencia, con un tamaño medio de archivo de PowerPoint de 10 MB (sin vídeo incrustado) o 30 MB (con vídeo incrustado). Promedio de 20 anotaciones por pizarra.  <br/> • El 20 % agrega vídeo. De estos usuarios, el 70 % está en conferencias habilitadas para vídeo de vista múltiple, en las que cada usuario recibe de 2 a 3 secuencias de vídeo.  <br/> • El 15 % agrega notas compartidas.  <br/> |
|Distribución de los participantes en las reuniones  <br/> |El 50 % corresponde a usuarios internos autenticados.  <br/> El 25 % corresponde a usuarios remotos autenticados.  <br/> El 15 % corresponde a usuarios anónimos.  <br/> El 10% corresponde a usuarios federados.  <br/> |
|Distribución de participación en las reuniones  <br/> |Se simula que los usuarios se unen a la reunión durante los primeros 5 minutos.  <br/> |
   
En los grupos de servidores front-end normales, Skype Empresarial Server tiene un tamaño máximo de reunión admitido de 250 usuarios. Cada grupo puede hospedar una reunión de 250 usuarios de una vez. Mientras tiene lugar esta gran reunión, el grupo también puede hospedar otras conferencias más pequeñas. Además, se pueden admitir reuniones de hasta 1.000 usuarios si se configura un grupo dedicado para hospedar estas reuniones. Para obtener más información, consulte [Plan for large meetings in Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md).
  
Las conferencias se simularon del modo siguiente.
  
- El 85 % de las conferencias contó con cuatro participantes.
    
- El 10 % de las conferencias contó con seis participantes.
    
- El 5 % de las conferencias contó con 11 participantes.
    
- Hubo una gran conferencia con 250 usuarios.
    
En la tabla siguiente se proporciona información detallada sobre el modelo de usuario para conferencias que incluye a usuarios de acceso telefónico local.
  
**Modelo de usuario de conferencias de acceso telefónico local**

|**Categoría**|**Descripción**|
|:-----|:-----|
|Autenticado/anónimo  <br/> |El 70 % de los autores de llamadas se une como anónimo y se le solicita un nombre registrado. El 30 % se une como usuario autenticado.  <br/> |
|Duración de la llamada y música en espera  <br/> |Duración media de llamada sin música en espera: 50 segundos.  <br/> El 50 % de los usuarios que llaman escucha música en espera durante una media de cinco minutos.  <br/> |
|Tono de marcado de frecuencia múltiple (DTMF)  <br/> |El 15 % de las conferencias de acceso telefónico local solo tiene coordinadores de teléfono. El 10 % de las conferencias mixtas que incluyen a usuarios de acceso telefónico local también tiene coordinadores de teléfono.  <br/> El 20 % de los coordinadores de teléfono usa dos comandos DTMF por conferencia.  <br/> |
|Idiomas del anuncio  <br/> |En las simulaciones se usa inglés como idioma del anuncio.  <br/> |
   
En la tabla siguiente se proporciona información detallada sobre el modelo de usuario para salas de espera de conferencia.
  
**Modelo de usuario para salas de espera de conferencia**

|**Categoría**|**Descripción**|
|:-----|:-----|
|Número de usuarios en sala de espera  <br/> |El 5 % de los usuarios de acceso telefónico local pasa por la sala de espera y el 25 % de otros usuarios también.  <br/> |
|Admisión desde la sala de espera  <br/> |En las simulaciones, el moderador admitió a todos los usuarios antes de que transcurriera el tiempo de espera de cliente.  <br/> |
   
En la tabla siguiente se describe el modelo de usuario para otras sesiones punto a punto.
  
**Modelo de usuario para sesiones punto a punto**

|**Categoría**|**Descripción**|
|:-----|:-----|
|Uso compartido de aplicaciones  <br/> |Cada usuario participa en 5 sesiones de uso compartido de aplicaciones de punto a punto al mes, para una media de 0,25 sesiones al día.  <br/> |
|Transferencia de archivos  <br/> |Cada usuario participa en 1 sesión de transferencia de archivos de punto a punto al mes (como parte de una sesión de MI), para una media de 0,05 sesiones al día. El tamaño de archivo medio transferido por sesión es de 1 MB.  <br/> |
   
La siguiente tabla describe el modelo de usuario de las directivas.
  
**Modelo de usuario de directivas**

|**Categoría**|**Descripción**|
|:-----|:-----|
|Conferencias, presencia y directivas de archivado  <br/> |Se supone que hay una directiva global, 10 directivas de conferencia de etiqueta, 4 directivas de archivado y 10 directivas de presencia de etiqueta.  <br/> |
|Directiva de voz  <br/> |Se supone que hay una directiva global y 2 directivas de etiqueta por sitio. El 100 % de los sitios tiene una directiva de sitio y el 30 % de los usuarios tiene asignada una directiva por usuario. Se supone un plan de marcado por sitio y dos rutas por sitio.  <br/> |
   
## <a name="busy-hour"></a>Hora punta

Para sesiones de punto a punto, la carga máxima se calcula con Intentos de llamada en hora punta (BHCA). Este término del sector de la voz presupone que el 50 % de todas las llamadas del día se realizará en el 20 % del tiempo. Se calcula con la siguiente fórmula:
  
 `BHCA=(total calls * 0.5) / 1.6`
  
Las pruebas de rendimiento han simulado hora punta ejecutando VoIP y otras sesiones de punto a punto en una carga de hora punta para al menos 1,6 horas por día.
  
En la carga máxima de conferencia se supone que el 75 % de todas las conferencias para un día de ocho horas tiene lugar en cuatro horas punta. Estas horas punta tienen 1,5 veces la carga media de conferencia.
  
## <a name="enterprise-voice-to-pstn-calls"></a>Telefonía IP empresarial a llamadas RTC

Las siguientes suposiciones se aplican a Telefonía IP empresarial llamadas:
  
- El 60 % de los usuarios están habilitados para Telefonía IP empresarial y el 60 % de estos usuarios están habilitados para llamadas RTC.
    
- Cada uno de estos usuarios habilitados para las llamadas RTC realiza 4 llamadas RTC durante la hora punta. Cada llamada dura 3 minutos.
    
- El 65 % de estas llamadas de voz RTC usa desvío de medios.
    
## <a name="mobility"></a>Movilidad

Se supone que el 40 % de los usuarios registrados está habilitado para la movilidad. Para cada usuario que tiene la movilidad habilitada, se supone que la actividad del cliente móvil se suma a la de las demás instancias de MPOP para dicho usuario, salvo las interacciones de conferencia, para las que el cliente de movilidad es solo otro tipo de cliente que se puede usar para participar en las conferencias.
  
## <a name="persistent-chat"></a>Chat persistente

Se supone que el 25 % de los usuarios registrado participará en sesiones de chat persistentes, con las siguientes características:
  
- Una media de 1,5 salones de chat por usuario.
    
- Cada salón de chat genera 12 peticiones de sondeo por hora, con una media de 10 destinatarios cada una.
    
## <a name="response-group-and-call-park"></a>Grupo de respuesta y estacionamiento de llamadas

Se supone que el 0,15 % de los usuarios registrados pertenece a grupos de respuesta. Se supone que el 0,02 % de los usuarios registrados tiene llamadas estacionadas en un momento determinado.
  

