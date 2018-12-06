---
title: 'Lync Server 2013: Habilitación de usuarios para E9-1-1'
TOCTitle: Habilitación de usuarios para E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48274998
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitación de usuarios para E9-1-1 en Lync Server 2013

 

_**Última modificación del tema:** 2012-06-06_

Durante el registro de clientes, Lync Server usa una directiva de ubicación para configurar las propiedades de E9-1-1 de los usuarios habilitados para Enterprise Voice. Esta directiva contiene la configuración que define cómo se implementa E9-1-1. Por ejemplo, la directiva de ubicación contiene información como la cadena de marcado de emergencia y si es necesario que un usuario introduzca manualmente una ubicación cuando el Servicio de información de ubicaciones no proporciona una automáticamente. Para obtener una descripción completa de una directiva de ubicación, consulte [Definir una directiva de ubicación para Lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Lync Server puede asignar una directiva de ubicación a los clientes basados en una subred o a usuarios basados en una directiva por usuario, por sitio o global. Para ayudarle a decidir cómo habilitará los usuarios, debe responder en primer lugar las siguientes preguntas.

  - **¿Piensa habilitar todos los usuarios o limitar la compatibilidad a zonas geográficas específicas de la empresa?**  
    Puede asignar una ubicación a todos los usuarios de la empresa mediante una directiva de ubicación global. Sin embargo, si asigna una directiva de ubicación a un sitio de red Lync Server y luego agrega subredes al sitio, puede limitar la compatibilidad con E9-1-1 a ubicaciones seleccionadas de la empresa y especificar el comportamiento de enrutamiento de E9-1-1 por sitio.

<!-- end list -->

  - **¿Piensa habilitar usuarios individuales a través de una directiva de usuario?**  
    Puede asignar directivas de ubicación directamente a usuarios específicos u objetos de contactos telefónicos de un área común si desea personalizar la compatibilidad con E9-1-1.

<!-- end list -->

  - **Cuando los clientes se desplazan fuera de la red o se encuentran en una subred no definida en la red, ¿deben los clientes seguir habilitados en E9-1-1?**  
    Si los usuarios tienen asignada una directiva de ubicación global, de sitio o por usuario, se puede requerir que los usuarios introduzcan manualmente una ubicación en el cliente si este no se encuentra en una subred definida o si el Servicio de información de ubicaciones no ha definido ninguna ubicación. Para obtener más información, consulte [Definir la experiencia de usuario para adquirir manualmente una ubicación en Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).

