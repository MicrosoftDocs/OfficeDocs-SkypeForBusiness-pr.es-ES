---
title: 'Lync Server 2013: Habilitar estacionamiento de llamadas para los usuarios'
TOCTitle: Habilitar estacionamiento de llamadas para los usuarios
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48276049
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar estacionamiento de llamadas para los usuarios en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-11_

Los usuarios no pueden estacionar llamadas ni recuperar llamadas estacionadas mientras no estén habilitados para Estacionamiento de llamadas en la directiva de voz.


> [!NOTE]
> De forma predeterminada, la aplicación Estacionamiento de llamadas está deshabilitada para todos los usuarios.



Puede habilitar Estacionamiento de llamadas para un ámbito global, de sitio o de usuario. El ámbito de usuario tiene prioridad sobre el ámbito de sitio y el ámbito de sitio tiene prioridad sobre el ámbito global. Si tiene varias directivas de voz, revise todas las directivas para habilitar Estacionamiento de llamadas, y no solamente la directiva global.

## Para habilitar Estacionamiento de llamadas para usuarios mediante Panel de control de Lync Server

1.  Inicie sesión en el equipo como miembro del grupo **RTCUniversalServerAdmins** , o bien como miembro del rol administrativo **CsVoiceAdministrator** , **CsServerAdministrator** o **CsAdministrator** .

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** .

4.  Haga clic en la pestaña **Directiva de voz** .

5.  Haga doble clic en una directiva de voz existente para abrir el cuadro de diálogo **Editar directiva de voz** .

6.  En **Características de llamada** , seleccione **Habilitar Estacionamiento de llamadas** .

7.  Haga clic en **Aceptar** para guardar la directiva de voz.

## Para habilitar Estacionamiento de llamadas para usuarios mediante cmdlets

1.  Inicie sesión en el equipo como un miembro del grupo RTCUniversalServerAdmins o bien, como un miembro del rol administrativo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    Por ejemplo, para habilitar el Estacionamiento de llamadas para la directiva de voz global predeterminada:
    
        Set-CsVoicePolicy -EnableCallPark $true

## Vea también

#### Tareas

[Crear una directiva de voz y configurar registros de uso de RTC en Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)

