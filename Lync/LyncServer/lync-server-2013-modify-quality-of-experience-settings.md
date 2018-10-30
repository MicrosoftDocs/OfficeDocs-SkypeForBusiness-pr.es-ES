---
title: Modificación de la configuración de la calidad de la experiencia
TOCTitle: Modificación de la configuración de la calidad de la experiencia
ms:assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182563(v=OCS.15)
ms:contentKeyID: 48276200
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modificación de la configuración de la calidad de la experiencia

 

_**Última modificación del tema:** 2013-02-23_

De forma predeterminada, los datos de calidad de la experiencia (QoE)se depuran una vez hayan transcurrido 60 días. Puede usar la configuración de la página **Datos de calidad de la experiencia** para conservar los datos durante un periodo de tiempo mayor o menor. Si deshabilita QoE, los datos que se recopilaron antes de que se habilitara se someterán también a la depuración.


> [!NOTE]
> Configure el registro de detalles de la llamada (CDR) y QoE para que conserven los datos durante el mismo número de días. Cada llamada en el registro de detalles de la llamada (CDR), que se encuentra disponible en la página principal de los informes del servidor de supervisión, incluye la información del CDR y de la QoE. Si la duración de la depuración para los CDR y la QoE es diferente, es posible que algunas llamadas solo incluyan datos de CDR, mientras que otras solo incluirán datos de la QoE.



El procedimiento siguiente describe cómo establecer la configuración de la depuración para los datos de la QoE.

## Para especificar la retención de los datos de la QoE mediante Panel de control de Lync Server

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Datos sobre la calidad de la experiencia**.

4.  En la página **Calidad de la experiencia**, haga clic en el sitio apropiado de la tabla, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.

5.  Para activar la depuración, seleccione **Habilitar depuración de QoE**.

6.  En **Conservar QoE durante un máximo de (días)** Seleccione el número máximo de días durante los que se deben conservar los datos de la QoE.

7.  Haga clic en **Confirmar**.

## Para especificar la retención de la QoE mediante los cmdlets de Windows PowerShell

Puede crear configuraciones de retención de la QoE utilizando Windows PowerShell y los cmdlets de **Set-CsQoEConfiguration**. Puede ejecutar este cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para especificar la retención de la QoE de una ubicación específica

  - Este comando permite habilitar la depuración de datos de la QoE en el sitio de Redmond, así como configurar el sitio de manera que mantenga los datos de la QoE durante 20 días.
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

## Para especificar la retención de la QoE de varias ubicaciones

  - Este comando permite configurar la retención de todas las opciones de configuración de QoE que se usan en una organización.
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

Para obtener más información, consulte el tema de ayuda correspondiente al cmdlet [Set-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsQoEConfiguration).

## Vea también

#### Otros recursos

[Implementación de supervisión en Lync Server 2013](lync-server-2013-deploying-monitoring.md)

