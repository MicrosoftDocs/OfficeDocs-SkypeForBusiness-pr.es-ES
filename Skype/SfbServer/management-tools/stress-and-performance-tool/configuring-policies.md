---
title: Configuración de directivas para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configuración de directivas para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015.
ms.openlocfilehash: bb049d5740d74e5ebeacd8a21d00e2644da61a7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815040"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Configuración de directivas para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015
 
Configuración de directivas para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015.
  
Hay varias directivas y otras áreas que puede configurar en Skype Empresarial Server 2015, antes de ejecutar la Herramienta de esfuerzo y rendimiento:
  
- [Directiva de archivado](configuring-policies.md#ArchivingPolicy)
    
- [Directiva de conferencia](configuring-policies.md#ConferencingPolicy)
    
- [Directiva de contactos](configuring-policies.md#ContactsPolicy)
    
- [Directiva de federación](configuring-policies.md#FederationPolicy)
    
- [Directiva de control de admisión de llamadas](configuring-policies.md#CACPolicy)
    
- [Reglas de enrutamiento de voz](configuring-policies.md#VoiceRoutingRules)
    
- [Aplicación Operador de conferencia](configuring-policies.md#ConfAttendantApp)
    
- [Servicio de estacionamiento de llamadas de servidor](configuring-policies.md#ServerCallParkServ)
    
- [Llamadas de emergencia](configuring-policies.md#EmergencyCalls)
    
- [Configuración de la aplicación grupo de respuesta](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Directiva de archivado
<a name="ArchivingPolicy"> </a>

Si tiene un servidor de archivado implementado en la topología de Skype Empresarial Server, puede ver el script ArchivingPolicy.ps1 cliente. Si necesita más ayuda, consulte los cmdlets de archivado y conferencia web.
  
## <a name="conferencing-policy"></a>Directiva de conferencia
<a name="ConferencingPolicy"> </a>

Para las conferencias, tenemos el script MeetingPolicy.ps1 conferencia. Si necesita más ayuda, consulte los cmdlets de conferencia web.
  
## <a name="contacts-policy"></a>Directiva de contactos
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1 script será el ejemplo que tendrás que revisar. Los cmdlets de mensajería instantánea y presencia le ayudarán si necesita más referencias.
  
## <a name="federation-policy"></a>Directiva de federación
<a name="FederationPolicy"> </a>

El script de ejemplo para federación es FederationPolicy.ps1. Los cmdlets que se revisarán, si necesita más información, serán el servidor perimetral, la federación y el acceso externo.
  
## <a name="call-admission-control-policy"></a>Directiva de control de admisión de llamadas
<a name="CACPolicy"> </a>

Puede hacer referencia a BandwidthPolicy.ps1 para esta directiva. Los cmdlets de control de admisión de llamadas también tendrán más información.
  
## <a name="voice-routing-rules"></a>Reglas de enrutamiento de voz
<a name="VoiceRoutingRules"> </a>

Necesitará el script de ejemplo RoutingRules.ps1 para el enrutamiento de voz. Al configurar estas reglas, tome nota del contexto del teléfono (es decir, /Perfil de ubicación o /SimpleName) y códigos de área interno/externo, para que pueda especificarlas al crear usuarios. También los necesitará durante la configuración de LyncPerfTool (específicamente para RTC-UC y UC-RTC).
  
Por ejemplo, el parámetro SimpleName en la llamada al cmdlet **New-CsDialPlan** en el ejemplo RoutingRules.ps1 debe usarse para el valor LocationProfile en la siguiente figura de UserProfileGenerator.exe:
  
![Herramienta de configuración de carga de Skype Empresarial, pestaña Escenarios de voz, Configuración avanzada para conversaciones.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Para obtener más información, puede revisar los Telefonía IP empresarial cmdlets.
  
## <a name="conference-attendant-application"></a>Aplicación Operador de conferencia
<a name="ConfAttendantApp"> </a>

En primer lugar, revise ConferenceAutoAttendantConfiguration.ps1 script. Necesitará tener en cuenta el número de teléfono ConferencingAutoAttendant (11211111111111 de forma predeterminada), de modo que pueda escribirlo en la herramienta de configuración LyncPerfTool para la generación de configuración, como se muestra a continuación:
  
![La pestaña Escenarios de voz que muestra el nivel de carga de conferencia y el número de teléfono.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Encontrará más detalles en los cmdlets de conferencia y conferencia de acceso telefónico local.
  
## <a name="server-call-park-service"></a>Servicio de estacionamiento de llamadas de servidor
<a name="ServerCallParkServ"> </a>

En realidad, está deshabilitado de forma predeterminada. Puede revisar el script CallParkConfiguration.ps1 ejemplo si necesita probarlo. Además, consulte los cmdlets de aplicación de estacionamiento de llamadas según sea necesario.
  
## <a name="emergency-calls"></a>Llamadas de emergencia
<a name="EmergencyCalls"> </a>

Deberá realizar los siguientes pasos para configurar las pruebas de esfuerzo y rendimiento para llamadas de emergencia:
  
1. Configurar una ruta de voz para llamadas de emergencia. Puede usar el script RoutingRules.ps1 y consultar el comentario **"Ruta E911** a RTC" para ver un ejemplo de cómo configurar esta ruta de voz.
    
    > [!CAUTION]
    > El comando de ejemplo RoutingRules.ps1 tiene un patrón de número que incluye el número 119 en lugar del 911. Debe evitar el uso del 911 (o su número de emergencia local real) para evitar llamadas accidentales a los operadores de emergencia locales durante las pruebas de carga. Recuerde que esta configuración es solo para fines de simulación. 
  
2. Configure las direcciones rellenando  los valores de la pestaña Configuración del servicio de información de ubicación en UserProvisioningTool, como se muestra en la ilustración siguiente:
    
     ![Herramienta de aprovisionamiento de usuarios que muestra el número de direcciones, subredes, conmutadores y puertos.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Cuando haya escrito todo en UserProvisioningTool, haga clic en el botón Generar archivos **de configuración LIS.**
    
4. Ahora se generarán archivos CSV para puertos, subredes, conmutadores y puntos de acceso inalámbrico (WAP), así como un archivo XML para la herramienta Stress and Performance. Puede usar los archivos CSV para las entradas al configurar el servicio de información de ubicación (LIS) con el script LisConfiguration.ps1 ubicación. Para ello, tendrás que mover el archivo Locations0.xml a la misma carpeta que el ejecutable de la Herramienta de esfuerzo y rendimiento (LyncPerfTool.exe). Esto le permitirá ejecutar escenarios de perfil de ubicación (plan de marcado).
    
## <a name="configuring-response-group-application"></a>Configuración de la aplicación grupo de respuesta
<a name="ConfigResponseGroupApp"> </a>

El script de ejemplo es ResponseGroupConfiguration.ps1. También hay cmdlets de aplicación de Grupo de respuesta para consultar más detalles de configuración. En el siguiente diagrama se mostrarán algunos de los detalles de configuración:
  
![La herramienta de configuración de grupo de respuesta que muestra los flujos de trabajo existentes para realizar pruebas.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

