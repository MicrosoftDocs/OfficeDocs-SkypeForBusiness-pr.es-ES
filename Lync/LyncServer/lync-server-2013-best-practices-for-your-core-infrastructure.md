---
title: Procedimientos recomendados para la infraestructura básica en Lync Server 2013
TOCTitle: Procedimientos recomendados para la infraestructura básica en Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn518328(v=OCS.15)
ms:contentKeyID: 60505973
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Procedimientos recomendados para la infraestructura básica en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Es probable que ya haya tomado las medidas necesarias para diseñar la tolerancia a errores en el sistema, mediante el uso de prácticas como garantizar la redundancia de hardware, la protección frente a interrupciones del suministro eléctrico, realizar instalaciones rutinarias de las actualizaciones de seguridad y las medidas contra virus, además de la supervisión de la actividad del servidor. Estas prácticas no solo resultarán de utilidad a su infraestructura de Microsoft Lync Server 2013, además de a toda su red. Si no ha implementado estas prácticas, le recomendamos que lo haga antes de implementar Lync Server 2013.

Para ayudarle a proteger los servidores de su implementación de Lync Server 2013 de daños accidentales o intencionados que pudieran provocar tiempos de inactividad, adopte las siguientes precauciones:

  - Mantenga actualizados los servidores con las actualizaciones de seguridad. Al suscribirse al Servicio de notificación de seguridad de Microsoft, se garantiza que recibirá notificación inmediata de las nuevas versiones de los boletines de seguridad de los productos de Microsoft. Para suscribirse, vaya al sitio web de Notificaciones de seguridad técnicas de Microsoft en [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202).

  - Asegúrese de que los derechos de acceso estén correctamente configurados.

  - Mantenga los servidores en un entorno físico que evite el acceso no autorizado. Asegúrese de que haya un software antivirus adecuado instalado en todos los servidores. Mantenga el software actualizado con los archivos de firma de virus más recientes. Utilice la función de actualización automática de la aplicación de antivirus para mantener las firmas de virus actualizadas.

  - Recomendamos desactivar los servicios del sistema operativo Windows Server que no sean necesarios en los equipos donde se instale Lync Server 2013.

  - Cifre los sistemas operativos y las unidades de disco en los que se encuentren almacenados los datos mediante un sistema de cifrado de todo el volumen, a menos que pueda garantizar un control constante y completo de los servidores, aislamiento físico total y la retirada correcta y segura de las unidades de disco que se sustituyan o fallen.

  - Deshabilite todos los puertos de Acceso directo a memoria (DMA) del servidor, a menos que pueda garantizar un control muy estricto del acceso físico a los servidores. Los ataques basados en DMA, que pueden iniciarse de una forma muy sencilla, pueden exponer información confidencial muy delicada, como es el caso de las claves de cifrado privadas.

