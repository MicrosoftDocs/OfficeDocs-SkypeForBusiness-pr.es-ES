---
title: "Conf. un itinéraire des communications vocales E9-1-1 dans Lync Server 2013"
TOCTitle: "Conf. un itinéraire des communications vocales E9-1-1 dans Lync Server 2013"
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48275539
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar una ruta de voz de E9-1-1 en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-17_

Para implementar E9-1-1, deberá configurar primero una ruta de voz para llamadas de emergencia. Para obtener información sobre cómo crear rutas de voz, consulte [Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md). Puede definir más de una ruta si, por ejemplo, su implementación incluye un tronco SIP principal y otro secundario.


> [!NOTE]
> Para incluir información de ubicación en una solicitud E9-1-1 INVITE, deberá configurar primero el tronco&nbsp;SIP que se conecta al proveedor de servicios E9-1-1 para enrutar las llamadas de emergencia por la puerta de enlace. Para ello, establezca la marca EnablePIDFLOSupport del cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> en True (el valor predeterminado de EnablePIDFLOSupport es False). Por ejemplo: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE><BR>No es necesario habilitar las ubicaciones de recepción para puertas de enlace de Red telefónica conmutada (RTC) de conmutación por error o para puertas de enlace de número de identificación de ubicación de emergencia (ELIN).



Para obtener más información acerca de trabajar con rutas de voz, consulte la documentación del Shell de administración de Lync Server con relación a los siguientes cmdlets:

  - **Set-CsPstnUsage**

  - **Get-CsPstnUsage**

  - **New-CsVoiceRoute**

  - **Get-CsVoiceRoute**

  - **Set-CsVoiceRoute**

  - **Remove-CsVoiceRoute**

## Para configurar una ruta de voz de E9-1-1

1.  Inicie sesión en el equipo con una cuenta que sea miembro de los grupos RTCUniversalServerAdmins o del rol administrativo CsVoiceAdministrator.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute el siguiente cmdlet para crear un nuevo registro de uso de RTC.
    
    Debe ser el mismo nombre que vaya a usar para la configuración de **RTC** en la directiva de ubicación. Aunque la implementación va a tener varios registros de uso telefónico, en el siguiente ejemplo se agrega “Uso para emergencias” a la lista actual de usos de de RTC disponibles. Para obtener más información, consulte [Configurar directivas de voz y registros de uso de la RTC para autorizar características y privilegios de llamada en Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  Ejecute el siguiente cmdlet para crear una nueva ruta de voz usando el registro de uso de RTC creado en el paso anterior.
    
    El patrón numérico debe coincidir con el patrón numérico que se usa en la configuración de **Cadena de marcado de emergencia** en la directiva de ubicación. El signo “+” es necesario porque Lync agrega “+” a las llamadas de emergencia. "Co1-pstngateway-1" es el identificador del servicio de tronco SIP del proveedor de servicios E9-11. En el siguiente ejemplo se usa “EmergencyRoute” como nombre de la ruta de voz.
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  Opcionalmente, en las conexiones de tronco SIP se recomienda ejecutar el siguiente cmdlet para crear una ruta local para llamadas que no administra el tronco SIP del proveedor de servicios E9-11. Esta ruta se usará en el caso de que la conexión con el proveedor de servicios de E9-11 no esté disponible.
    
    En el siguiente ejemplo se da por hecho que el usuario tiene un uso “Local” en su directiva de voz.
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

