---
title: Configuración de directivas para el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configuración de directiva de Skype para Business Server 2015 herramienta de esfuerzo y rendimiento.
ms.openlocfilehash: c5dd20df0cac3121169f6eb5659eb6339d7875e2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32236190"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Configuración de directivas para el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento
 
Configuración de directiva de Skype para Business Server 2015 herramienta de esfuerzo y rendimiento.
  
Existen varias directivas y otras áreas que puede configurar en Skype para Business Server 2015, antes de ejecutar la herramienta de rendimiento y esfuerzo:
  
- [Directiva de archivado](configuring-policies.md#ArchivingPolicy)
    
- [Directiva de conferencia](configuring-policies.md#ConferencingPolicy)
    
- [Directiva de contactos](configuring-policies.md#ContactsPolicy)
    
- [Directiva de federación](configuring-policies.md#FederationPolicy)
    
- [Directiva de Control de admisión de llamadas](configuring-policies.md#CACPolicy)
    
- [Reglas de enrutamiento de voz](configuring-policies.md#VoiceRoutingRules)
    
- [Aplicación de operador de conferencia](configuring-policies.md#ConfAttendantApp)
    
- [Servicio de estacionamiento de llamadas de servidor](configuring-policies.md#ServerCallParkServ)
    
- [Llamadas de emergencia](configuring-policies.md#EmergencyCalls)
    
- [Aplicación de configuración de grupo de respuesta](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Directiva de archivado
<a name="ArchivingPolicy"> </a>

Si tiene un servidor de archivado implementado en su Skype para la topología de servidor empresarial, puede buscar en la secuencia de comandos ArchivingPolicy.ps1. Si necesita más ayuda, desproteger los cmdlets de archivado y conferencias Web.
  
## <a name="conferencing-policy"></a>Directiva de conferencia
<a name="ConferencingPolicy"> </a>

Para las conferencias, tenemos el script MeetingPolicy.ps1. Si necesita más ayuda, desproteger los cmdlets de conferencias Web.
  
## <a name="contacts-policy"></a>Directiva de contactos
<a name="ContactsPolicy"> </a>

Secuencia de comandos de ContactsPolicy.ps1 será el ejemplo que necesitará para revisar. Los cmdlets de mensajería instantánea y presencia le ayudará a si necesita más referencias.
  
## <a name="federation-policy"></a>Directiva de federación
<a name="FederationPolicy"> </a>

El script de ejemplo para la federación es FederationPolicy.ps1. Los cmdlets para revisar, si necesita más insight, será el servidor perimetral, la federación y el acceso externo.
  
## <a name="call-admission-control-policy"></a>Directiva de Control de admisión de llamadas
<a name="CACPolicy"> </a>

Puede hacer referencia a BandwidthPolicy.ps1 para esta directiva. Los cmdlets de Control de admisión de llamadas tendrá más información así como.
  
## <a name="voice-routing-rules"></a>Reglas de enrutamiento de voz
<a name="VoiceRoutingRules"> </a>

Necesitará el script de ejemplo RoutingRules.ps1 para el enrutamiento de voz. Cuando está configurando estas reglas, tome nota del contexto de teléfono (es decir, /Location perfil o /SimpleName) y códigos de área internas y externas, por lo que puede especificar al crear usuarios. También necesitará ellos durante la configuración de LyncPerfTool (específicamente para UC de RTC y UC-RTC).
  
Por ejemplo, se debe usar el parámetro SimpleName en la llamada al cmdlet **New-CsDialPlan** en el ejemplo de RoutingRules.ps1 para el valor de LocationProfile en la siguiente ilustración de UserProfileGenerator.exe:
  
![Herramienta de configuración de carga de Skype Empresarial, ficha Escenarios de voz, Configuración avanzada para conversaciones.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Para obtener información detallada, puede revisar los cmdlets de Enterprise Voice.
  
## <a name="conference-attendant-application"></a>Aplicación de operador de conferencia
<a name="ConfAttendantApp"> </a>

En primer lugar, revise la secuencia de comandos ConferenceAutoAttendantConfiguration.ps1. Desea tome nota del número de teléfono de ConferencingAutoAttendant (1121111111 de forma predeterminada), para que pueda escribir en la herramienta de configuración de LyncPerfTool para la generación de la configuración, como sigue:
  
![Pestaña Escenarios de voz donde se muestra el número de teléfono y el nivel de Carga de conferencia.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Encontrará más detalles en la conferencia y conferencia de acceso telefónico cmdlets.
  
## <a name="server-call-park-service"></a>Servicio de estacionamiento de llamadas de servidor
<a name="ServerCallParkServ"> </a>

Esto realmente está deshabilitada de forma predeterminada. Puede revisar el script de ejemplo CallParkConfiguration.ps1 si necesita probar esto. Además, desproteger los cmdlets de aplicación de estacionamiento de llamadas según sea necesario.
  
## <a name="emergency-calls"></a>Llamadas de emergencia
<a name="EmergencyCalls"> </a>

Debe realizar los siguientes pasos para configurar de esfuerzo y pruebas de rendimiento para las llamadas de emergencia:
  
1. Configurar una ruta de voz para llamadas de emergencia. Puede utilizar la secuencia de comandos RoutingRules.ps1 y comprobar bajo el comentario " **Ruta E911 a RTC** " para obtener un ejemplo de cómo configurar la ruta de voz.
    
    > [!CAUTION]
    > El comando de ejemplo en RoutingRules.ps1 tiene un patrón de número que incluye la cantidad 119 en lugar de 911. Se debe evitar usar 911 (o su número de emergencia local real) para evitar que las llamadas accidentales a los operadores de emergencias locales durante las pruebas de carga. Recuerde, esta configuración es únicamente con fines de simulación! 
  
2. Configure las direcciones rellenar los valores en la ficha **Configuración del servicio de información de ubicación** en la UserProvisioningTool, tal como se muestra en la ilustración siguiente:
    
     ![Herramienta Aprovisionamiento de usuarios donde se muestra el número de direcciones, subredes, conmutadores y puertos.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Cuando todo lo que ha especificado en el UserProvisioningTool, haga clic en el botón **Generar archivos de configuración de LIS** .
    
4. Ahora se generará archivos CSV para puertos, subredes, conmutadores y puntos de acceso inalámbrico (WAP), así como un archivo XML para la herramienta de esfuerzo y rendimiento. Puede usar los archivos CSV para entradas al configurar el servicio de información de ubicación (LIS) con la secuencia de comandos LisConfiguration.ps1. Para ello, debe mover el archivo Locations0.xml a la misma carpeta que la herramienta Stress and Performance ejecutable (LyncPerfTool.exe). Esto le permitirá ejecutar escenarios (plan de marcado) de perfil de ubicación.
    
## <a name="configuring-response-group-application"></a>Aplicación de configuración de grupo de respuesta
<a name="ConfigResponseGroupApp"> </a>

El script de ejemplo es ResponseGroupConfiguration.ps1. También hay cmdlets de aplicación de grupo de respuesta para revisar para obtener más información de configuración. En el siguiente diagrama se muestra algunos de los detalles de configuración:
  
![Herramienta de configuración de grupo de respuesta donde se muestran los flujos de trabajo existentes para pruebas.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

