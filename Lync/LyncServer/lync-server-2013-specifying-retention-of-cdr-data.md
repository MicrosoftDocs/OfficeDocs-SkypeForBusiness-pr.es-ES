---
title: "Spécif. de la rétention des données de l’enregistrement des détails des appels"
TOCTitle: "Spécif. de la rétention des données de l’enregistrement des détails des appels"
ms:assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182581(v=OCS.15)
ms:contentKeyID: 48276546
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Especificación de la conservación de datos de CDR

 

_**Última modificación del tema:** 2013-02-23_

De forma predeterminada, los datos del registro detallado de llamadas (CDR) se purgan una vez transcurridos 60 días. Puede usar la configuración de la página **Registro detallado de llamadas** para conservar los datos durante un periodo de tiempo mayor o menor. Si deshabilita CDR, los datos que se recopilaron antes de habilitarlo también se someterán a la purga.


> [!NOTE]
> Configure CDR y la calidad de la experiencia (QoE) para que conserven los datos durante el mismo número de días. Cada llamada de CDR, que se encuentra disponible en la página web Informes del Servidor de supervisión, incluye la información de QoE y CDR. Si la duración de la purga es diferente para CDR y QoE, es posible que algunas llamadas solo incluyan datos de CDR y otras solo de QoE.



Use los procedimientos siguientes para configurar la purga de los datos de CDR.

## Para especificar la retención de los datos de CDR:

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación de la izquierda, haga clic en **Supervisión y archivado** y en **Registro de detallado de llamadas**.

4.  En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la tabla, en **Editar** y en **Mostrar detalles**.

5.  Para activar la purga, seleccione **Habilitar depuración de registros de detalles de llamadas (CDR)**.

6.  En **Conservar registros de detalles de llamadas durante un máximo de (días):**, seleccione el número máximo de días que desea retener los registros detallados de llamadas.

7.  En **Conservar los datos de los informes de errores durante el período de duración máximo (días):**, seleccione el número máximo de días que desea retener los registros de error.

8.  Haga clic en **Confirmar**.

## Para especificar la retención de CDR con los cmdlets de Shell de administración de Lync Server:

Puede definir la configuración de retención de CDR con Windows PowerShell y el cmdlet Set-CsCdrConfiguration. Ejecute este cmdlet desde Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para especificar la retención de CDR para una ubicación determinada:

  - Este comando habilita la purga de los datos de CDR para el sitio de Redmond y configura el sitio para conservar los datos de CDR y de los registros de errores durante 20 días.
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

## Para especificar la retención de CDR para varias ubicaciones:

  - Este comando configura la retención de CDR para todos los valores de configuración de CDR que se usan en una organización.
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

Para más información, consulte el tema de Ayuda del cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration).

## Vea también

#### Otros recursos

[Registro de detalles de llamadas (CDR)](lync-server-2013-call-detail-recording-cdr.md)

