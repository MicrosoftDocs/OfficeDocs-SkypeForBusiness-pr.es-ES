---
title: "Lync Server 2013: Definir experiencia de usuario para adquirir ubicación manualmente"
TOCTitle: Definir la experiencia de usuario para adquirir manualmente una ubicación
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398912(v=OCS.15)
ms:contentKeyID: 48276777
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definir la experiencia de usuario para adquirir manualmente una ubicación en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-03_

Si un cliente está ubicado fuera de la red, o en una subred indefinida, puede introducir manualmente una ubicación. No obstante, durante una llamada de emergencia, se enrutará la llamada a un distribuidor del centro de respuesta de llamadas de emergencia (ECRC) E9-1-1 nacional y/o regional antes de enrutarla a un punto de respuesta de seguridad pública (PSAP). El distribuidor del ECRC preguntará la ubicación verbalmente a la persona que realice la llamada y después desviará la llamada al PSAP adecuado en función de la información proporcionada.

  - **¿Se debe pedir a los usuarios que especifiquen una ubicación si el Servicio de información de ubicaciones no proporciona una automáticamente?**  
    Por ejemplo, si un cliente se encuentra en una subred no definida, en casa, en una cafetería o en cualquier otro lugar fuera de la red, ¿se debe obligar al usuario a especificar una ubicación?
    
    Puede configurar el valor de **Ubicación obligatoria** en la directiva de ubicación para definir el comportamiento del cliente. Si se define este valor en No, no se pedirá al usuario una ubicación. Si se define en Sí, se pedirá al usuario una ubicación, pero este puede anular la solicitud. Si se define en Declinación de responsabilidades, se pedirá al usuario una ubicación y se le mostrará una declinación de responsabilidades si intenta anular la solicitud. En todos los casos, el usuario puede continuar usando el cliente de la forma habitual.

Cuando un usuario especifica una ubicación, esta se asigna, en función de la dirección MAC de la puerta de enlace predeterminada de la red del cliente, y se almacena en una tabla de usuarios locales ubicada en el cliente. Cuando el cliente vuelve a cualquier ubicación almacenada previamente, se define automáticamente en dicha ubicación. Los usuarios también pueden seleccionar manualmente cualquier ubicación que esté almacenada en la tabla de usuarios locales y administrar las entradas existentes.


> [!NOTE]
> Solo puede modificar la ubicación actual del cliente, pero también puede eliminar cualquier ubicación que esté almacenada en la tabla de usuarios locales.


