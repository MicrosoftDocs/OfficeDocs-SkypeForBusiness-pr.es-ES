---
title: 'Lync Server 2013: definir la Directiva de ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b0e9aca4b3e66202d6b3c4a47b90db4f207fda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a>Definir la Directiva de ubicación de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

Cada directiva de ubicación contiene la información siguiente:

  - **Servicios de emergencia habilitados**  
    Cuando este valor es **sí**, el cliente está habilitado para E9-1-1. Cuando un cliente se registra, intenta adquirir una ubicación desde el servicio de información de ubicación e incluirá la información de ubicación como parte de una llamada de emergencia.

<!-- end list -->

  - **Ubicación requerida**  
    Esta configuración solo se usa cuando los **servicios de emergencia habilitados** están establecidos en **sí**.
    
    Puede configurar la configuración de **Ubicación requerida** para definir el comportamiento del cliente. Si se define el valor en **No**, no se pedirá al usuario una ubicación. Si se define en **Sí**, se pedirá al usuario una ubicación, pero este puede anular la solicitud. Si se define en **Declinación de responsabilidades**, el usuario deberá especificar una ubicación y se le mostrará una declinación de responsabilidades si intenta anular la solicitud. En todos los casos, el usuario puede seguir utilizando el cliente.
    
    <div>
    

    > [!NOTE]  
    > El texto de declinación de responsabilidades no aparecerá si el usuario ha introducido manualmente una ubicación antes de ser habilitado para E9-1-1 y los usuarios que ya hayan visto la declinación de responsabilidades no recibirán las actualizaciones de dicho texto. 

    
    </div>

<!-- end list -->

  - **Declinación de responsabilidades del servicio de emergencia mejorado**  
    En esta configuración se especifica la declinación de responsabilidad que los usuarios ven si rechazan la solicitud de una ubicación. En Lync Server 2013, puede usar la Directiva de ubicación para establecer distintas renuncias para diferentes configuraciones regionales o conjuntos de usuarios diferentes.
    
    <div>
    

    > [!NOTE]  
    > Esta configuración de directiva de ubicación difiere de Lync Server 2010, donde se usaba el cmdlet <STRONG>set-CsEnhancedEmergencyServiceDisclaimer</STRONG> para establecer un aviso de declinación de responsabilidades global para toda la organización. Si ya existe un aviso de declinación de responsabilidades global, debe especificar esa renuncia en la Directiva de ubicación. Es decir, Lync Server 2013 solo usa descargos de responsabilidad especificados en la Directiva de ubicación.

    
    </div>

<!-- end list -->

  - **Cadena de marcado de emergencia**  
    Esta cadena de marcado (menos el "+" inicial, pero incluida la normalización que realiza el plan de marcado del usuario de Lync) significa que una llamada es una llamada de emergencia. La **cadena de marcado de emergencia** implica que el cliente incluya la información de la devolución de llamadas y de la ubicación con la llamada.
    
    <div>
    

    > [!NOTE]  
    > Si su organización no usa un prefijo de acceso de línea externa, no es necesario crear una regla de normalización de plan de marcado correspondiente que agregue un signo "+" a la cadena de 911 antes de enviar la llamada al enrutamiento de salida en un servidor de grupo de Lync. el cliente de Lync agrega automáticamente el prefijo "+" como resultado de la Directiva de ubicación. Sin embargo, si su sitio utiliza un prefijo de acceso externo, debe agregar una regla de normalización a la directiva de plan de marcado correspondiente que quite el prefijo de acceso externo y agregue el signo “+”. Por ejemplo, si su ubicación usa un prefijo de acceso externo de 9 y un usuario marca&nbsp;9 911 para realizar una llamada de emergencia, el cliente usará su Directiva de plan de marcado para normalizarlo a + 911 antes de que las rutas de la ubicación del autor de la llamada evalúen el número marcado. perfiles.

    
    </div>

<!-- end list -->

  - **Máscaras de cadena de marcado de emergencia**  
    Lista separada por punto y coma de cadenas de marcado que se traduce en la **cadena de marcado de emergencia**especificada. Por ejemplo, es posible que desee agregar 112, que es el número de servicio de emergencia de la mayor parte de Europa. Es posible que un usuario de Lync que visite Europa no sepa que 911 es el número de emergencia de Estados Unidos, pero sí puede marcar 112 y obtener el mismo resultado. Al igual que con la cadena de marcado de emergencia, no incluya un signo "+" antes de cada número y, si usa códigos de acceso de línea externa, asegúrese de que existen reglas de normalización en la Directiva del plan de marcado del usuario para quitar el dígito de código de acceso.

<!-- end list -->

  - **Uso de RTC**  
    El nombre del uso de RTC que contiene las rutas de acceso de enrutamiento que determinan a qué tronco SIP, a qué puerta de enlace RTC o a qué puerta de enlace ELIN se dirigen las llamadas de emergencia.
    
    <div>
    

    > [!NOTE]  
    > Solo se puede asignar un uso a una directiva de ubicación. Este uso de RTC reemplaza los usos de RTC asignados a la directiva de voz del usuario, pero solo se aplica a llamadas realizadas a la cadena de marcado de emergencia o a una de las máscaras de la cadena de marcado de emergencia.

    
    </div>

<!-- end list -->

  - **URI de notificación**  
    Especifica los URI de SIP del personal de seguridad para que reciban una notificación por mensajería instantánea cuando se realice una llamada de emergencia. Se admiten los grupos de distribución.

<!-- end list -->

  - **URI de conferencia**  
    Especifica el número de llamada directa a la extensión (DID) (normalmente un número del servicio de seguridad) que necesita incluirse en el modo de conferencia cuando se realiza una llamada de emergencia.  

<!-- end list -->

  - **Modo de conferencia**  
    Especifica si el URI de conferencia se incluirá en la llamada de emergencia en modo de conferencia a través de una comunicación unidireccional o bidireccional. 

<!-- end list -->

  - **Intervalo de actualización de la ubicación**  
    Especifica la cantidad de tiempo (en horas) entre las solicitudes de un cliente para una actualización de ubicación desde el servicio de información de ubicación. El valor puede ser cualquier número entre 1 y 12. El valor predeterminado es 4.

</div>

<span> </span>

</div>

</div>

</div>

