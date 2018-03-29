---
title: Configuración de directivas para el Skype para Business Server 2015 Stress y la herramienta de rendimiento
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configuración de directiva de Skype para Business Server 2015 Stress y la herramienta de rendimiento.
ms.openlocfilehash: 5bdeb4c65b3649e7d417550578e277e01e55fcc3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Configuración de directivas para el Skype para Business Server 2015 Stress y la herramienta de rendimiento
 
Configuración de directiva de Skype para Business Server 2015 Stress y la herramienta de rendimiento.
  
Existen varias directivas y otras áreas que se pueden configurar en Skype Business Server 2015, antes de ejecutar la herramienta de rendimiento y esfuerzo:
  
- [Directiva de archivado](configuring-policies.md#ArchivingPolicy)
    
- [Directiva de conferencia](configuring-policies.md#ConferencingPolicy)
    
- [Directiva de contactos](configuring-policies.md#ContactsPolicy)
    
- [Directiva de federación](configuring-policies.md#FederationPolicy)
    
- [Llamar a la directiva de Control de admisión](configuring-policies.md#CACPolicy)
    
- [Reglas de enrutamiento de voz](configuring-policies.md#VoiceRoutingRules)
    
- [Solicitud de operador de conferencia](configuring-policies.md#ConfAttendantApp)
    
- [Servicio de servidor llamada Park](configuring-policies.md#ServerCallParkServ)
    
- [Llamadas de emergencia](configuring-policies.md#EmergencyCalls)
    
- [Aplicación de configuración de grupo de respuesta](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Directiva de archivado
<a name="ArchivingPolicy"> </a>

Si tiene un servidor de archivado implementado en su Skype para la topología de servidores de negocios, puede mirar la secuencia de comandos ArchivingPolicy.ps1. Si necesita asistencia adicional, consulte los cmdlets archivado y conferencias Web.
  
## <a name="conferencing-policy"></a>Directiva de conferencia
<a name="ConferencingPolicy"> </a>

Para conferencias, tenemos la secuencia de comandos MeetingPolicy.ps1. Si necesita asistencia adicional, consulte los cmdlets de conferencias Web.
  
## <a name="contacts-policy"></a>Directiva de contactos
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1 secuencia de comandos será la muestra que debe revisar. Los cmdlets de mensajería instantánea y presencia ayudará si necesita más referencias.
  
## <a name="federation-policy"></a>Directiva de federación
<a name="FederationPolicy"> </a>

La secuencia de comandos de ejemplo para la federación es FederationPolicy.ps1. Los cmdlets para revisar, si necesita más información, será el servidor perimetral, la federación y el acceso externo.
  
## <a name="call-admission-control-policy"></a>Llamar a la directiva de Control de admisión
<a name="CACPolicy"> </a>

Puede hacer referencia a BandwidthPolicy.ps1 para esta directiva. Los cmdlets de Control de admisión de llamadas tendrá más información así.
  
## <a name="voice-routing-rules"></a>Reglas de enrutamiento de voz
<a name="VoiceRoutingRules"> </a>

Tendrá la secuencia de comandos de ejemplo RoutingRules.ps1 para el enrutamiento de voz. Para configurar estas reglas, tome nota del contexto de teléfono (es decir, sobre el perfil o /SimpleName) y los códigos de área internas y externas, para que pueda especificar al crear usuarios. Les necesitará también durante la configuración de LyncPerfTool (específicamente para PSTN-UC y UC-PSTN).
  
Por ejemplo, el parámetro SimpleName en la llamada al cmdlet **New-CsDialPlan** en el ejemplo RoutingRules.ps1 debe utilizarse para el valor de LocationProfile en la siguiente figura de UserProfileGenerator.exe:
  
![Herramienta de configuración de carga de Skype Empresarial, ficha Escenarios de voz, Configuración avanzada para conversaciones.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Para obtener más información, puede revisar los cmdlets de Telefonía IP empresarial.
  
## <a name="conference-attendant-application"></a>Solicitud de operador de conferencia
<a name="ConfAttendantApp"> </a>

Revisar la secuencia de comandos ConferenceAutoAttendantConfiguration.ps1. Desea tomar nota del número de teléfono de ConferencingAutoAttendant (1121111111 de forma predeterminada), para que puedan introducir en la herramienta de configuración de LyncPerfTool para la generación de la configuración, como sigue:
  
![Pestaña Escenarios de voz donde se muestra el número de teléfono y el nivel de Carga de conferencia.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Encontrará más detalles en la conferencia y conferencia telefónica de cmdlets.
  
## <a name="server-call-park-service"></a>Servicio de servidor llamada Park
<a name="ServerCallParkServ"> </a>

En realidad no está habilitado de forma predeterminada. Si necesita probar esto puede revisar la secuencia de comandos de ejemplo CallParkConfiguration.ps1. Además, consulte los cmdlets llame al parque aplicación según sea necesario.
  
## <a name="emergency-calls"></a>Llamadas de emergencia
<a name="EmergencyCalls"> </a>

Debe realizar los pasos siguientes para configurar el estrés y pruebas de rendimiento para las llamadas de emergencia:
  
1. Establecer una ruta de voz para llamadas de emergencia. Puede utilizar la secuencia de comandos RoutingRules.ps1 y comprobar bajo el comentario " **E911 ruta a RTC** " para obtener un ejemplo de cómo establecer esta ruta de voz.
    
    > [!CAUTION]
    > El comando de ejemplo en RoutingRules.ps1 tiene un patrón de número que incluye el número 119 en lugar de 911. Debe evitar el uso de 911 (o su número de emergencia local real) para evitar llamadas accidentales a los operadores de emergencia locales durante las pruebas de carga. Recuerde que esta configuración es sólo con fines de simulación! 
  
2. Configurar direcciones rellenando los valores en la ficha **Configuración del servicio de información de ubicación** en la UserProvisioningTool, como se muestra en la figura siguiente:
    
     ![Herramienta Aprovisionamiento de usuarios donde se muestra el número de direcciones, subredes, conmutadores y puertos.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Cuando haya insertado todos los elementos en el UserProvisioningTool, haga clic en el botón **Generar archivos de configuración de LIS** .
    
4. Ahora se generarán archivos CSV para puertos, subredes, conmutadores y puntos de acceso inalámbrico (WAP), así como un archivo XML para la herramienta de carga y rendimiento. Puede utilizar los archivos CSV para entradas al configurar el servicio de información de ubicación (LIS) con el script LisConfiguration.ps1. Para ello, debe mover el archivo Locations0.xml en la misma carpeta que la herramienta Stress and Performance ejecutable (LyncPerfTool.exe). Esto le permitirá ejecutar escenarios (dial plan) de perfil de ubicación.
    
## <a name="configuring-response-group-application"></a>Aplicación de configuración de grupo de respuesta
<a name="ConfigResponseGroupApp"> </a>

La secuencia de comandos de ejemplo es ResponseGroupConfiguration.ps1. También hay cmdlets de aplicación de grupo de respuesta a revisar para obtener más información de configuración. El diagrama siguiente muestra algunos de los detalles de configuración:
  
![Herramienta de configuración de grupo de respuesta donde se muestran los flujos de trabajo existentes para pruebas.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

