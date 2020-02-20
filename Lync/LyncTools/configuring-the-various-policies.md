---
title: Configuración de las distintas directivas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17116443361749bd3bcce75d5a9d38a08a3ba95c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a>Configuración de las distintas directivas

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

<div>

## <a name="configuring-the-various-policies"></a>Configuración de las distintas directivas

Estas son las diversas directivas que puede configurar en su topología de Lync Server 2013, antes de ejecutar la herramienta de esfuerzo y rendimiento de Lync Server 2013.

<div>

## <a name="configuring-the-archiving-policy"></a>Configuración de la Directiva de archivado

Vea el script de ejemplo ArchivingPolicy. ps1. Debe usar este script solo si se ha implementado un servidor de archivado en la topología. Para obtener más información, consulte la documentación de Lync Server 2013 y la ayuda del cmdlet para los [cmdlets de archivado y supervisión en Lync Server 2013](https://technet.microsoft.com/library/gg415629\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a>Configuración de la Directiva de conferencia

Vea el script de ejemplo MeetingPolicy. ps1. Para obtener más información, consulte la documentación de Lync Server 2013 y la ayuda del cmdlet para los [cmdlets de conferencia web en Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-contacts-policy"></a>Configuración de la Directiva de contactos

Vea el ejemplo ContactsPolicy. ps1. Para obtener más información, consulte la documentación de Lync Server 2013 y la ayuda del cmdlet para los [cmdlets de mensajería instantánea y presencia en Lync Server 2013](https://technet.microsoft.com/library/gg398611\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-federation-policy"></a>Configuración de la Directiva de Federación

Vea el ejemplo FederationPolicy. ps1. Para obtener más información, consulte la documentación de Lync Server 2013 y la ayuda del cmdlet para los [cmdlets del servidor perimetral en Lync server 2013](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) y los [cmdlets de Federación y acceso externo en Lync Server 2013](https://technet.microsoft.com/library/gg415651\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a>Configuración de la Directiva de control de admisión de llamadas

Vea el ejemplo BandwidthPolicy. ps1. Para obtener más información, consulte la documentación de Lync Server 2013 [Overview of Call Admission Control en Lync server 2013](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) y la ayuda del cmdlet para [cmdlets de control de admisión de llamadas en Lync Server 2013](https://technet.microsoft.com/library/gg415676\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a>Configuración de las reglas de enrutamiento de voz

Vea el ejemplo RoutingRules. ps1. Al configurar las reglas de enrutamiento de voz, tenga en cuenta el contexto del teléfono (es decir, el perfil de/Location o/SimpleName) y los códigos de área interna/externa para que pueda especificarlos al crear usuarios y durante la configuración de LyncPerfTool (específicamente para RTC-UC y UC-RTC). Por ejemplo, el parámetro SimpleName en la llamada al cmdlet **New-CsDialPlan** en el ejemplo de RoutingRules. PS1 debe usarse para el valor LocationProfile de la siguiente figura de UserProfileGenerator. exe.

![Regla de enrutamiento de voz de muestra.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Regla de enrutamiento de voz de muestra.")

Para obtener más información, consulte la documentación de Lync Server 2013 y la ayuda del cmdlet para los [cmdlets de Enterprise Voice en Lync Server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a>Configuración de la aplicación de operador de conferencia

Vea el ejemplo ConferenceAutoAttendantConfiguration. ps1. Anote el número de teléfono ConferencingAutoAttendant (1121111111, de forma predeterminada), para que pueda escribirlo en la herramienta de configuración de herramientas de LyncPerf para la generación de la configuración.

![Configuración de la aplicación operador de conferencia](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configuración de la aplicación operador de conferencia")

Para obtener más información, consulte la documentación de Lync Server 2013 y la ayuda del cmdlet de los [cmdlets de conferencia web en Lync server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) y los [cmdlets de conferencia de acceso telefónico local en Lync Server 2013](https://technet.microsoft.com/library/gg415630\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a>Configuración del servicio de estacionamiento de llamadas de Lync Server

El estacionamiento de llamadas está deshabilitado de forma predeterminada. Vea el ejemplo CallParkConfiguration. ps1. Para obtener más información, consulte la documentación de Lync Server 2013 y la ayuda del cmdlet para los [cmdlets de aplicación de estacionamiento de llamadas en Lync Server 2013](https://technet.microsoft.com/library/gg415639\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-emergency-calls"></a>Configuración de llamadas de emergencia

Realice los pasos siguientes para configurar las pruebas de esfuerzo y rendimiento de las llamadas de emergencia.

1.  Configurar una ruta de voz para las llamadas de emergencia. Vea el script RoutingRules. PS1 bajo el comentario "Route E911 to RTC" para obtener un ejemplo de cómo configurar esta ruta de voz.
    
    <div>
    

    > [!WARNING]  
    > El comando de ejemplo de RoutingRules. PS1 tiene un patrón de números que incluye el número 119 en lugar de 911. Debe evitar usar 911 (o el número de emergencia local real) para evitar llamadas accidentales a los operadores de emergencia locales durante las pruebas de carga. Esta configuración se usa solo con fines de simulación.

    
    </div>

2.  Configure las direcciones rellenando los valores de la pestaña **Lis** en la UserProvisioningTool, como se muestra en la siguiente figura.
    
    ![Configurar el servicio de información de ubicación.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configurar el servicio de información de ubicación.")  

3.  Haga clic en **generar archivos de configuración de lis**.

4.  Se generan archivos CSV para puertos, subredes, conmutadores y puntos de acceso inalámbrico (WAP), y un archivo XML para la herramienta de esfuerzo y rendimiento de Lync Server 2013. Los archivos CSV se deben usar como entradas (en la misma carpeta) al configurar el servicio de información de ubicación (LIS) con el script LisConfiguration. ps1. Mueva el archivo Locations0. XML generado a la misma carpeta que el archivo ejecutable de la herramienta stress and performance de Lync Server 2013 (LyncPerfTool. exe), que ejecutará los escenarios de Perfil de ubicación (plan de marcado).

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a>Creación, habilitación, configuración y deshabilitación de usuarios

Debe crear todos los usuarios antes de ejecutar los siguientes scripts. Siga las instrucciones en [crear usuarios y contactos](create-users-and-contacts.md) para crear usuarios. Para obtener más información, consulte la documentación del cmdlet de Lync Server 2013 para los cmdlets [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [set-CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\))y [Disable-CsUser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) .

</div>

<div>

## <a name="configuring-response-group-application"></a>Configuración de la aplicación de grupo de respuesta

Vea el ejemplo ResponseGroupConfiguration. ps1. Para obtener más información, consulte la documentación de Lync Server 2013 y la ayuda del cmdlet para los [cmdlets de la aplicación de grupo de respuesta en Lync Server 2013](https://technet.microsoft.com/library/gg415654\(v=ocs.15\)). Para revisar la configuración de la aplicación del grupo `https://<poolfqdn>/RgsConfig/`de respuesta, consulte, como se muestra en la ilustración siguiente.

![Herramienta de configuración del grupo de respuesta.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "Herramienta de configuración del grupo de respuesta.")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

