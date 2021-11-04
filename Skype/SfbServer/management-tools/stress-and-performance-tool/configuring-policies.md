---
title: Configuración de directivas para la Skype Empresarial Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configuración de directivas para Skype Empresarial Server 2015 Stress and Performance Tool.
ms.openlocfilehash: ba08b12b94847ac130a5f95770ad9cf4c71e0e8c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771996"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Configuración de directivas para la Skype Empresarial Server 2015 Stress and Performance Tool
 
Configuración de directivas para Skype Empresarial Server 2015 Stress and Performance Tool.
  
Hay varias directivas y otras áreas que puede configurar en Skype Empresarial Server 2015, antes de ejecutar la Herramienta de esfuerzo y rendimiento:
  
- [Directiva de archivado](configuring-policies.md#ArchivingPolicy)
    
- [Directiva de conferencia](configuring-policies.md#ConferencingPolicy)
    
- [Directiva de contactos](configuring-policies.md#ContactsPolicy)
    
- [Directiva de federación](configuring-policies.md#FederationPolicy)
    
- [Directiva de control de admisión de llamadas](configuring-policies.md#CACPolicy)
    
- [Reglas de enrutamiento de voz](configuring-policies.md#VoiceRoutingRules)
    
- [Aplicación operador de conferencia](configuring-policies.md#ConfAttendantApp)
    
- [Servicio de estacionamiento de llamadas de servidor](configuring-policies.md#ServerCallParkServ)
    
- [Llamadas de emergencia](configuring-policies.md#EmergencyCalls)
    
- [Configuración de la aplicación grupo de respuesta](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Directiva de archivado
<a name="ArchivingPolicy"> </a>

Si tiene un servidor de archivado implementado en la topología Skype Empresarial Server, puede ver el script ArchivingPolicy.ps1 archivo. Si necesita más ayuda, consulte los cmdlets archivado y conferencia web.
  
## <a name="conferencing-policy"></a>Directiva de conferencia
<a name="ConferencingPolicy"> </a>

Para conferencias, tenemos el MeetingPolicy.ps1 script. Si necesita más ayuda, consulte los cmdlets de conferencia web.
  
## <a name="contacts-policy"></a>Directiva de contactos
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1 script será el ejemplo que tendrás que revisar. Los cmdlets de mensajería instantánea y presencia le ayudarán si necesita más referencias.
  
## <a name="federation-policy"></a>Directiva de federación
<a name="FederationPolicy"> </a>

El script de ejemplo para federación es FederationPolicy.ps1. Los cmdlets que se revisarán, si necesita más información, serán servidor perimetral, federación y acceso externo.
  
## <a name="call-admission-control-policy"></a>Directiva de control de admisión de llamadas
<a name="CACPolicy"> </a>

Puede hacer referencia a BandwidthPolicy.ps1 para esta directiva. Los cmdlets de control de admisión de llamadas también tendrán más información.
  
## <a name="voice-routing-rules"></a>Reglas de enrutamiento de voz
<a name="VoiceRoutingRules"> </a>

Necesitará el script de ejemplo RoutingRules.ps1 para enrutamiento de voz. Al configurar estas reglas, tome nota del contexto del teléfono (es decir, /Perfil de ubicación o /SimpleName) y Códigos de área internos/externos, de modo que pueda especificarlos al crear usuarios. También los necesitará durante la configuración de LyncPerfTool (específicamente para RTC-UC y UC-RTC).
  
Por ejemplo, el parámetro SimpleName de la llamada al cmdlet **New-CsDialPlan** del ejemplo RoutingRules.ps1 debe usarse para el valor LocationProfile en la siguiente figura de UserProfileGenerator.exe:
  
![Skype Empresarial de configuración de carga, pestaña Escenarios de voz, Configuración avanzada para conversaciones.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Para obtener más información, puede revisar los Telefonía IP empresarial cmdlets.
  
## <a name="conference-attendant-application"></a>Aplicación operador de conferencia
<a name="ConfAttendantApp"> </a>

Primero revise el ConferenceAutoAttendantConfiguration.ps1 script. Querrá tomar nota del número de teléfono de ConferencingAutoAttendant (1121111111 de forma predeterminada), de modo que pueda escribirlo en la herramienta de configuración lyncPerfTool para la generación de configuración, como se muestra a continuación:
  
![La pestaña Escenarios de voz que muestra el nivel de carga de conferencia y el número de teléfono.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Encontrará más detalles en los cmdlets de conferencia y conferencia de acceso telefónico local.
  
## <a name="server-call-park-service"></a>Servicio de estacionamiento de llamadas de servidor
<a name="ServerCallParkServ"> </a>

Esto está deshabilitado de forma predeterminada. Puede revisar el script CallParkConfiguration.ps1 ejemplo si necesita probar esto. Además, consulte los cmdlets de aplicación de estacionamiento de llamadas según sea necesario.
  
## <a name="emergency-calls"></a>Llamadas de emergencia
<a name="EmergencyCalls"> </a>

Deberá realizar los siguientes pasos para configurar las pruebas de esfuerzo y rendimiento para llamadas de emergencia:
  
1. Configurar una ruta de voz para llamadas de emergencia. Puede usar el script RoutingRules.ps1 y comprobar en el comentario " **Route E911 to PSTN** " un ejemplo de cómo configurar esta ruta de voz.
    
    > [!CAUTION]
    > El comando de ejemplo RoutingRules.ps1 tiene un patrón de números que incluye el número 119 en lugar de 911. Debe evitar usar 911 (o su número de emergencia local real) para evitar llamadas accidentales a los operadores de emergencia locales durante las pruebas de carga. Recuerde que esta configuración es solo para fines de simulación. 
  
2. Configure las direcciones rellenando los valores de la pestaña **Configuración** del servicio de información de ubicación en UserProvisioningTool, como se muestra en la siguiente figura:
    
     ![Herramienta de aprovisionamiento de usuarios que muestra el número de direcciones, subredes, conmutadores y puertos.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Cuando haya escrito todo en UserProvisioningTool, haga clic en **el botón Generar archivos de configuración lis.**
    
4. Ahora se generarán archivos CSV para puertos, subredes, conmutadores y puntos de acceso inalámbrico (WAP), así como un archivo XML para la herramienta Stress and Performance. Puede usar los archivos CSV para las entradas al configurar el servicio de información de ubicación (LIS) con el script LisConfiguration.ps1 ubicación. Para ello, deberá mover el archivo Locations0.xml a la misma carpeta que el ejecutable de la herramienta de esfuerzo y rendimiento (LyncPerfTool.exe). Esto le permitirá ejecutar escenarios de perfil de ubicación (plan de marcado).
    
## <a name="configuring-response-group-application"></a>Configuración de la aplicación grupo de respuesta
<a name="ConfigResponseGroupApp"> </a>

El script de ejemplo es ResponseGroupConfiguration.ps1. También hay cmdlets de aplicación de grupo de respuesta para revisar para obtener más detalles de configuración. En el siguiente diagrama se mostrarán algunos de los detalles de configuración:
  
![La herramienta de configuración grupo de respuesta que muestra flujos de trabajo existentes para pruebas.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

