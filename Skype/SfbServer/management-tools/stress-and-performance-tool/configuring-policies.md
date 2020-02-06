---
title: Configuración de directivas para la herramienta de estrés y rendimiento de Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Configuración de directivas para la herramienta de estrés y rendimiento de Skype empresarial Server 2015.
ms.openlocfilehash: bfdf0d9875a37f7f4a1f98aa24cd6fd5c3176a00
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816199"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Configuración de directivas para la herramienta de estrés y rendimiento de Skype empresarial Server 2015
 
Configuración de directivas para la herramienta de estrés y rendimiento de Skype empresarial Server 2015.
  
Hay varias directivas y otras áreas que puede configurar en Skype empresarial Server 2015, antes de ejecutar la herramienta estrés and Performance:
  
- [Directiva de archivado](configuring-policies.md#ArchivingPolicy)
    
- [Directiva de conferencia](configuring-policies.md#ConferencingPolicy)
    
- [Directiva de contactos](configuring-policies.md#ContactsPolicy)
    
- [Directiva de Federación](configuring-policies.md#FederationPolicy)
    
- [Directiva de control de admisión de llamadas](configuring-policies.md#CACPolicy)
    
- [Reglas de enrutamiento de voz](configuring-policies.md#VoiceRoutingRules)
    
- [Aplicación de operador de conferencia](configuring-policies.md#ConfAttendantApp)
    
- [Servicio de estacionamiento de llamadas de servidor](configuring-policies.md#ServerCallParkServ)
    
- [Llamadas de emergencia](configuring-policies.md#EmergencyCalls)
    
- [Configuración de la aplicación de grupo de respuesta](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Directiva de archivado
<a name="ArchivingPolicy"> </a>

Si tiene un servidor de archivado implementado en su topología de servidor de Skype empresarial, puede consultar el script ArchivingPolicy. ps1. Si necesita más ayuda, consulte los cmdlets de archivado y conferencias web.
  
## <a name="conferencing-policy"></a>Directiva de conferencia
<a name="ConferencingPolicy"> </a>

Para las conferencias, tenemos el script MeetingPolicy. ps1. Si necesita más ayuda, consulte los cmdlets de conferencias web.
  
## <a name="contacts-policy"></a>Directiva de contactos
<a name="ContactsPolicy"> </a>

El script ContactsPolicy. PS1 será el ejemplo que necesitarás revisar. Los cmdlets de presencia y mensajería instantánea le ayudarán si necesita más referencias.
  
## <a name="federation-policy"></a>Directiva de Federación
<a name="FederationPolicy"> </a>

El script de ejemplo para la Federación es FederationPolicy. ps1. Los cmdlets para revisar, si necesita más información, serán servidor perimetral, Federación y acceso externo.
  
## <a name="call-admission-control-policy"></a>Directiva de control de admisión de llamadas
<a name="CACPolicy"> </a>

Puede hacer referencia a BandwidthPolicy. PS1 para esta Directiva. Los cmdlets de control de admisión de llamadas también tendrán más información.
  
## <a name="voice-routing-rules"></a>Reglas de enrutamiento de voz
<a name="VoiceRoutingRules"> </a>

Necesitarás el script de ejemplo RoutingRules. PS1 para el enrutamiento de voz. Cuando configure estas reglas, tome nota del contexto de teléfono (es decir, perfil de/Location o/SimpleName) y códigos de área interna y externa para poder especificarlos al crear usuarios. También los necesitará durante la configuración de LyncPerfTool (específicamente para PSTN-UC y UC-PSTN).
  
Por ejemplo, el parámetro SimpleName en la llamada al cmdlet **New-CsDialPlan** en el ejemplo de RoutingRules. PS1 debe usarse para el valor LocationProfile de la siguiente ilustración de UserProfileGenerator. exe:
  
![Herramienta de configuración de carga de Skype Empresarial, ficha Escenarios de voz, Configuración avanzada para conversaciones.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Para obtener información detallada, puede revisar los cmdlets de telefonía IP empresarial.
  
## <a name="conference-attendant-application"></a>Aplicación de operador de conferencia
<a name="ConfAttendantApp"> </a>

Primero revise el script ConferenceAutoAttendantConfiguration. ps1. Querrá tomar nota del número de teléfono ConferencingAutoAttendant (1121111111 de forma predeterminada), de modo que pueda introducirlo en la herramienta de configuración de LyncPerfTool para la generación de configuración, como se indica a continuación:
  
![Pestaña Escenarios de voz donde se muestra el número de teléfono y el nivel de Carga de conferencia.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Encontrará más información en los cmdlets conferencias y conferencias de acceso telefónico local.
  
## <a name="server-call-park-service"></a>Servicio de estacionamiento de llamadas de servidor
<a name="ServerCallParkServ"> </a>

En realidad, esto está deshabilitado de forma predeterminada. Puede revisar el script de ejemplo CallParkConfiguration. PS1 si necesita probarlo. Además, consulte los cmdlets de la aplicación Parque de llamadas según sea necesario.
  
## <a name="emergency-calls"></a>Llamadas de emergencia
<a name="EmergencyCalls"> </a>

Para configurar las pruebas de estrés y rendimiento para llamadas de emergencia, tendrá que realizar los siguientes pasos:
  
1. Configura una ruta de voz para llamadas de emergencia. Puede usar el script RoutingRules. PS1 y comprobar en el comentario " **Route E911 to RTC** " para obtener un ejemplo de cómo configurar esta ruta de voz.
    
    > [!CAUTION]
    > El comando de ejemplo en RoutingRules. PS1 tiene un patrón de números que incluye el número 119 en lugar de 911. Debes evitar usar 911 (o tu número de emergencia local) para evitar llamadas accidentales a tus operadores de emergencia locales durante las pruebas de carga. Recuerde que esta configuración solo es para fines de simulación. 
  
2. Configure las direcciones rellenando los valores de la pestaña **Ubicación información de configuración del servicio** en la UserProvisioningTool, como se muestra en la siguiente ilustración:
    
     ![Herramienta Aprovisionamiento de usuarios donde se muestra el número de direcciones, subredes, conmutadores y puertos.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Cuando haya escrito todo en la UserProvisioningTool, haga clic en el botón **generar archivos de configuración Lis** .
    
4. Ahora se generarán los archivos CSV para puertos, subredes, conmutadores y puntos de acceso inalámbrico (WAP), así como un archivo XML para la herramienta de carga y rendimiento. Puede usar los archivos CSV para entradas al configurar el servicio de información de ubicación (LIS) con el script LisConfiguration. ps1. Para ello, tendrá que mover el archivo Locations0. XML a la misma carpeta que el ejecutable de la herramienta de carga y rendimiento (LyncPerfTool. exe). Esto le permitirá ejecutar escenarios de Perfil de ubicación (plan de marcado).
    
## <a name="configuring-response-group-application"></a>Configuración de la aplicación de grupo de respuesta
<a name="ConfigResponseGroupApp"> </a>

El script de ejemplo es ResponseGroupConfiguration. ps1. También hay cmdlets de aplicación de grupo de respuesta para revisar para obtener más información sobre la configuración. En el diagrama siguiente se mostrarán algunos de los detalles de configuración:
  
![Herramienta de configuración de grupo de respuesta donde se muestran los flujos de trabajo existentes para pruebas.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

