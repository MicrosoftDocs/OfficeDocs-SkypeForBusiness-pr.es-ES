---
title: 'Lync Server 2013: Definición de requisitos para conferencias'
TOCTitle: Definición de requisitos para conferencias
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48275396
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definición de requisitos para conferencias en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-30_

Al determinar qué funcionalidades de conferencia se van a implementar, es necesario tener en cuenta las características que quiere poner a disposición de los usuarios, así como la capacidad de ancho de banda de la red. La siguiente lista de preguntas le orientará en el proceso de planeación de una conferencia para saber qué características de conferencia debe implementar en función de los requisitos de su organización.

  - **¿Desea habilitar la conferencia web, que incluye la colaboración con documentos y el uso compartido de aplicaciones?**
    
    En caso afirmativo, debe habilitar la conferencia para el Grupo de servidores front-end en la Microsoft Lync Server 2013, herramienta de planeación o en el Generador de topologías. Al habilitar las conferencias, se permiten tanto las conferencias web como las conferencias A/V.
    
    Uso compartido de aplicaciones requiere y utiliza más ancho de banda de red de colaboración en documentos. Lync Server 2013 proporciona un mecanismo de límite para controlar cada aplicación de uso compartido de sesión. De forma predeterminada, esto se establece en 1,5 KB por segundo para cada sesión.
    
    Si no desea habilitar el uso compartido de aplicaciones, pero sí colaborar en los documentos, puede habilitar las conferencias y usar las directivas de reunión para deshabilitar el uso compartido de aplicaciones. Para obtener información detallada sobre la configuración de directivas de reunión, consulte [Directivas de conferencia de Lync Server 2013](lync-server-2013-conferencing-policies.md).
    
    Para dejar que los usuarios compartan presentaciones de PowerPoint, es necesario configurar el Servidor Office Web Apps. Para obtener información detallada sobre cómo configurar el Servidor Office Web Apps, consulte [Configuración de la integración de Office Web Apps Server y Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **¿Desea habilitar la conferencia A/V?**
    
    En caso afirmativo, debe habilitar la conferencia para el Grupo de servidores front-end en la Lync Server 2013, herramienta de planeación o en el Generador de topologías. Al habilitar las conferencias, se permiten tanto las conferencias web como las conferencias A/V.
    
    Las conferencias A/V requieren y usan más ancho de banda que las conferencias web (lo que incluye la colaboración en documentos y los recursos compartidos de aplicaciones). Si no desea habilitar las conferencias A/V, pero sí las conferencias web, puede habilitar las conferencias y usar las directivas de reunión para deshabilitar las conferencias A/V.
    
    Si desea habilitar las conferencias de audio pero no videoconferencias, puede habilitar la conferencia A/V y usar las directivas de reunión para evitar las conferencias de vídeo. Como alternativa, puede habilitar la conferencia A/V y habilitar únicamente determinados usuarios para que inicien o participen en conferencias A/V.
    

    > [!NOTE]
    > No se necesita Telefonía IP empresarial para usar las conferencias A/V. Si habilita las conferencias A/V, los usuarios que dispongan de dispositivos de audio podrán agregar audio a las conferencias, aun cuando se use una PBX como solución de telefonía.



  - **¿Desea habilitar a los usuarios para que se unan a la parte de audio de las conferencias al usar un teléfono RTC?**
    
    Si es así, implemente y habilite la conferencia de acceso telefónico. Los usuarios invitados, tanto dentro como fuera de su organización, puede unirse entonces a la parte de audio de las conferencias mediante un teléfono RTC.

  - **¿Desea habilitar a los usuarios externos con los clientes de Lync Server 2013 para que se unan a los tipos de conferencias que ha habilitado?**
    
    En caso afirmativo, deberá implementar Servidores perimetrales. Al permitir la participación externa en reuniones, estará maximizando su inversión en Lync Server 2013. Por ejemplo, los usuarios con equipos portátiles con Lync Server 2013 se podrán unir a las conferencias desde cualquier sitio en el que se encuentren: en casa, en el aeropuerto o en las instalaciones de un cliente.
    
    Además, con los Servidores perimetrales implementados se pueden crear relaciones federadas con otras organizaciones, como los clientes o proveedores, y los usuarios de dichas organizaciones podrán colaborar más fácilmente con los usuarios de su organización.
    
    Para obtener información detallada sobre cómo implementar Servidores perimetrales, consulte [Planear acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) y [Implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md). Para obtener información detallada sobre cómo habilitar el acceso externo para el Servidor Office Web Apps, consulte [Publicación de Office Web Apps Server con un servidor proxy inverso en Lync Server 2013](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).

  - **¿Desea controlar a los clientes que pueden unirse a las reuniones de Lync Server 2013?**
    
    En caso afirmativo, deberá configurar una página de participación en la reunión para que solo estén disponibles las opciones de cliente que quiera permitir. Cada vez que un usuario hace clic en un vínculo para unirse a una reunión programada, Lync Server 2013 detecta si el cliente ya está instalado en el equipo. Luego inicia el cliente predeterminado y abre la página de participación en la reunión, que contiene vínculos para clientes alternativos. La página de participación en la reunión siempre contiene la opción para usar Microsoft Lync Web App. Además de esta opción, puede decidir si desea incluir vínculos para Asistente y para versiones anteriores de Communicator. Para obtener información detallada, consulte [Configuración de la página de participación en reuniones en Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).

## En esta sección

  - [Requisitos de conferencia web](lync-server-2013-web-conferencing-requirements.md)

  - [Requisitos de conferencias de audio y vídeo](lync-server-2013-a-v-conferencing-requirements.md)

  - [Planeación de las conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)

## Vea también

#### Otros recursos

[Planificar conferencias en Lync Server 2013](lync-server-2013-planning-for-conferencing.md)  
[Lista de comprobación para la implementación de conferencias en Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)

