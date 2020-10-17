---
title: 'Lync Server 2013: definir la Directiva de ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bdb3b556f5b9a8d552a3c48e300b8c4b7b19f5f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504527"
---
# <a name="defining-the-location-policy-for-lync-server-2013"></a>Definición de la Directiva de ubicación para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

Cada directiva de ubicación contiene la información siguiente:

  - **Servicios de emergencia habilitados**  
    Si se define en **Sí**, se habilita al cliente para E9-1-1. Cuando un cliente se registra, intenta adquirir una ubicación del servicio de información de ubicación e incluye la información de ubicación como parte de una llamada de emergencia.

<!-- end list -->

  - **Ubicación obligatoria**  
    Esta configuración solo se usa cuando los **servicios de emergencia habilitados**   están establecidos en **sí**.
    
    Configure el parámetro de **Ubicación obligatoria** para definir el comportamiento del cliente. Si se define el valor en **No**, no se pedirá al usuario una ubicación. Si se define en **Sí**, se pedirá al usuario una ubicación, pero este puede anular la solicitud. Si se define en **Declinación de responsabilidades**, el usuario deberá especificar una ubicación y no podrá anular la solicitud hasta que haya introducido una solicitud. En ambos casos el usuario puede continuar usando el cliente.
    
    <div>
    

    > [!NOTE]  
    > El texto de declinación de responsabilidades no aparecerá si el usuario ha introducido manualmente una ubicación antes de ser habilitado para E9-1-1 y los usuarios que ya hayan visto la declinación de responsabilidades no recibirán las actualizaciones de dicho texto.

    
    </div>

<!-- end list -->

  - **Declinación de responsabilidad de servicio de emergencia mejorado**  
    En esta configuración se especifica la declinación de responsabilidad que los usuarios ven si rechazan la solicitud de una ubicación. En Lync Server 2013, puede usar la Directiva de ubicación para establecer diferentes avisos de declinación de responsabilidad para diferentes configuraciones regionales o conjuntos de usuarios diferentes.
    
    <div>
    

    > [!NOTE]  
    > Esta configuración de directiva difiere de Lync Server 2010, donde se usa el cmdlet <STRONG>set-CsEnhancedEmergencyServiceDisclaimer</STRONG> para establecer una declinación de responsabilidades global para toda la organización. Si ya existe una declinación de responsabilidad global, especifique la declinación de responsabilidad en la directiva de ubicación. Es decir, Lync Server 2013 solo usa avisos de declinación de responsabilidad especificados en la Directiva de ubicación.

    
    </div>

<!-- end list -->

  - **Cadena de marcado de emergencia**  
    La cadena de marcado que indica que la llamada en cuestión es una llamada de emergencia. La **cadena de marcado de emergencia** comporta la adición a la llamada de información de ubicación y devolución de llamada por parte del cliente.
    
    <div>
    

    > [!NOTE]  
    > Si su organización no utiliza un prefijo de acceso de línea externo, no tendrá que crear una regla de normalización de planes de marcado correspondiente que añada un signo “+” a la cadena 911 antes de enviar la llamada al enrutamiento de salida en el servidor de grupo de Lync; el signo “+” se agregará automáticamente por parte del cliente de Lync como resultado de la directiva de ubicación. Sin embargo, si su sitio utiliza un prefijo de acceso externo, agregue una regla de normalización a la directiva de plan de marcado aplicable que quite el prefijo de acceso externo y agregue el signo “+”. Por ejemplo, si su ubicación usa un prefijo de acceso externo de 9 y un usuario marca 9 &nbsp; 911 para realizar una llamada de emergencia, el cliente usará su Directiva de plan de marcado para normalizarlo a + 911 antes de que las rutas del perfil de ubicación del autor de la llamada evalúen el número marcado.

    
    </div>

<!-- end list -->

  - **Máscaras de cadena de marcado de emergencia**  
    Una lista de cadenas de marcado separadas por caracteres de punto y coma que deben convertirse a la **cadena de marcado de emergencia** especificada. Por ejemplo, es posible que desee agregar 112, que es el número del servicio de emergencia para la mayor parte de Europa. Un usuario de Lync visitante proveniente de Europa puede que no sepa que el 911 es el número de emergencia en los Estados Unidos, pero puede marcar el 112 y obtener el mismo resultado. Al igual que con la cadena de marcado de emergencia, no incluya un signo “+” antes de cada número y, si utiliza códigos de acceso de línea externa, asegúrese de que existen reglas de normalización en la directiva del plan de marcado de los usuarios para quitar el dígito del código de acceso.

<!-- end list -->

  - **Uso de RTC**  
    El nombre del uso de RTC que contiene las rutas de acceso que determinan en qué tronco SIP o puerta de enlace RTC se realizarán las llamadas de emergencia.
    
    <div>
    

    > [!NOTE]  
    > Solo se puede asignar un uso a una directiva de ubicación. Este uso de RTC reemplaza los usos de RTC asignados a la directiva de voz del usuario, pero solo se aplica a llamadas realizadas a la cadena de marcado de emergencia o a una de las máscaras de la cadena de marcado de emergencia.

    
    </div>

<!-- end list -->

  - **URI de notificación**  
    Especifica los URI de SIP del personal de seguridad para que reciban una notificación por mensajería instantánea cuando se realice una llamada de emergencia. Se admiten los grupos de distribución.

<!-- end list -->

  - **URI de conferencia**  
    Especifica el número de llamada directa a la extensión (DID) (normalmente un número del departamento de seguridad) que debe incluirse en el modo de conferencia cuando se realiza una llamada de emergencia.

<!-- end list -->

  - **Modo de conferencia**  
    Especifica si el URI de conferencia se incluirá en la llamada de emergencia en modo conferencia mediante comunicación unidireccional o bidireccional.

<!-- end list -->

  - **Intervalo de actualización de la ubicación**  
    Especifica la cantidad de tiempo (en horas) entre las solicitudes de cliente para una actualización de ubicación desde el servicio de información de ubicación. El valor se puede definir en cualquier número incluido entre 1 y 12. El valor predeterminado es 4.

</div>

<span> </span>

</div>

</div>

</div>

