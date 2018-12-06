---
title: Información general sobre la respuestas de llamadas en grupo
TOCTitle: Información general sobre la respuestas de llamadas en grupo
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945623(v=OCS.15)
ms:contentKeyID: 52061656
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Información general sobre la respuestas de llamadas en grupo

 

_**Última modificación del tema:** 2013-02-12_

La atención de llamadas grupales, una nueva característica de las actualizaciones acumulativas de Lync Server 2013 de febrero de 2013, permite a los usuarios responder llamadas entrantes realizadas a sus compañeros de trabajo desde sus propios teléfonos. Esta nueva característica aumenta la disponibilidad de la línea de un usuario, ya que permite que otros usuarios respondan una llamada entrante marcando un número de grupo de atención de llamadas. Al implementar la atención de llamadas grupales, se puede reducir considerablemente el número de llamadas entrantes redirigidas al correo de voz, lo que resulta particularmente útil en el caso de llamadas de clientes ajenos a la organización.

La característica de atención de llamadas grupales se ha diseñado, particularmente, para unidades de negocio en entornos de oficina abiertos. Las llamadas entrantes no resultan molestas porque solo suenan en el destino previsto. Los otros usuarios que escuchan el timbre, no obstante, pueden responder la llamada muy fácilmente marcando el número del grupo.

En entornos donde los usuarios no se encuentran en un diseño de oficina abierto, o donde los usuarios que comparten una responsabilidad común están distribuidos geográficamente, la Llamada de equipo presenta la solución más adecuada. La principal diferencia entre la atención de llamadas grupales y la Llamada de equipo es que, con la atención de llamadas grupales, una llamada entrante solo suena en el destino previsto, pero cualquiera puede optar por responderla marcando un número de grupo. Con la Llamada de equipo, la llamada suena en los teléfonos de todos los integrantes del equipo y cualquiera de ellos puede responderla. Otra diferencia entre estas características es que la atención de llamadas grupales es administrada por un administrador a través de Lync Server. Con la Llamada de equipo, los usuarios finales administran la característica mediante el cliente de Lync. Con la atención de llamadas grupales, por lo tanto, se puede centralizar este aspecto de la administración de llamadas.

La atención de llamadas grupales se basa en el Aplicación de estacionamiento de llamadas. Al implementar la atención de llamadas grupales, configura la tabla de órbitas de estacionamiento de llamadas con intervalos de números de extensión independientes que se designan como números de grupo de atención de llamadas. Al igual que los números de órbita de estacionamiento de llamadas, los números de grupo de atención de llamadas deben ser extensiones virtuales que no tengan asignado ningún usuario o teléfono. Cada Grupo de servidores front-end donde implementa la atención de llamadas grupales puede tener uno o más intervalos de números de grupo de atención de llamadas. Los intervalos de números de grupo deben ser globalmente únicos en toda la implementación de Lync Server.


> [!NOTE]
> Los intervalos de números que se designan como números de atención de llamadas grupales en la tabla de órbitas de estacionamiento de llamadas no pueden administrarse ni visualizarse mediante Panel de control de Lync Server. El único modo de ver todos los intervalos de números de la tabla de órbitas de estacionamiento de llamadas es usar Shell de administración de Lync Server. De forma similar, el único modo de agregar, modificar o quitar números de atención de llamadas grupales es usar Shell de administración de Lync Server.



Una vez configurados los números de grupo de atención de llamadas, debe asignar los usuarios a un grupo de atención de llamadas. Las llamadas de un usuario asignado a un grupo de atención de llamadas pueden responderlas otros usuarios. Cuando entra una llamada para un usuario asignado a un grupo de atención de llamadas, cualquier otro usuario que escuche la llamada puede atenderla marcando de forma manual el número del grupo de atención de llamadas. No es necesario que el usuario que atiende la llamada sea miembro del grupo. Cuando otro usuario atiende una llamada, se envía una notificación al número al que se llamó originalmente.


> [!NOTE]
> Un usuario solo puede pertenecer a un grupo de atención de llamadas.




> [!NOTE]
> Si bien cualquier usuario de la implementación de Lync Server puede responder una llamada realizada a un miembro del grupo de atención de llamadas, la persona que lo hace debe marcar el número correcto del grupo de atención de llamadas.



Si un usuario marca el número de un grupo de atención de llamadas para responder una llamada cuando suenan varios teléfonos del grupo, atenderá la llamada que ha sonado por más tiempo.

La configuración de llamadas simultáneas resulta útil para los usuarios que disponen de la atención de llamadas grupales. Es decir, una llamada realizada a un usuario que dispone de la atención de llamadas grupales sonará en todos los destinos configurados y otro usuario podrá responderla. La excepción a esta regla es cuando un usuario configura las llamadas simultáneas para llamar a todos los integrantes del grupo.

La atención de llamadas grupales no se puede usar para responder los siguientes tipos de llamadas:

  - Llamadas a una línea privada

  - Llamadas de un contacto al que se ha asignado la relación de privacidad Amigos y familiares
    
    > [!TIP]  
    > Un usuario miembro de un grupo de atención de llamadas puede impedir que se recuperen ciertas llamadas mediante la atención de llamadas grupales marcando el contacto como personal en el cliente de Lync. Para marcar un contacto como personal, establezca la relación de privacidad del contacto en Amigos y familiares. Las llamadas provenientes de contactos con la relación de privacidad establecida en Amigos y familiares no se pueden recuperar mediante la atención de llamadas grupales.
    


  - Parte de vídeo de llamadas de audio y vídeo
    

    > [!NOTE]
    > Si un usuario responde una llamada de audio y vídeo, solo recibe el audio. La persona que llama o la persona que responde la llamada puede escalarla para agregar vídeo.



  - Llamadas simultáneas redirigidas a integrantes de Llamada de equipo

  - Llamadas redirigidas a un delegado

  - Llamadas redirigidas a un grupo de respuesta

Los siguientes tipos de usuarios no pueden participar en la atención de llamadas grupales. Es decir, no deben incluirse en un grupo de atención de llamadas grupales y no pueden responder llamadas de usuarios que tienen la atención de llamadas grupales habilitada.

  - Usuarios alojados en línea en una implementación híbrida

  - Usuarios que no están alojados en un grupo de Lync Server 2013 con las actualizaciones acumulativas de Lync Server 2013 de febrero de 2013 en una implementación local

Si nadie atiende una llamada realizada a un miembro de un grupo de atención de llamadas, la llamada se redirige según lo especificado en la configuración del cliente. Es decir, la llamada se desvía al correo de voz o se reenvía a otro destino, tal como se especifique en la configuración del cliente.

