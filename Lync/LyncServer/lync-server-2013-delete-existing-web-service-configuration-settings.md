---
title: Eliminación de la configuración de un servicio web existente
TOCTitle: Eliminación de la configuración de un servicio web existente
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48276591
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminación de la configuración de un servicio web existente

 

_**Última modificación del tema:** 2013-02-23_

Siga los pasos siguientes para eliminar una directiva de servicios web.

## Para eliminar una directiva de servicios web:

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Seguridad** y en **Servicio web**.

4.  En la página **Servicio web**, vaya al campo de búsqueda y escriba total o parcialmente el nombre de la directiva que desea eliminar.

5.  En la lista de directivas, haga clic en la directiva que desea, en **Editar** y en **Eliminar**.

6.  Haga clic en **Aceptar**.

## Eliminar los nuevos valores de configuración de los servicios web con los cmdlets de Shell de administración de Lync Server

También puede ver los valores de configuración de los servicios web a través de Shell de administración de Lync Server y el cmdlet **Remove-CsWebServiceConfiguration**. Ejecute este cmdlet desde Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para eliminar una colección específica de valores de configuración de los servicios web:

  - El comando siguiente quita los valores de seguridad de los servicios web que se aplican al sitio de Redmond:
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

## Para eliminar todos los valores de configuración de los servicios web que se aplican al ámbito del sitio:

  - El comando siguiente quita todos los valores de seguridad de los servicios web que se aplican al ámbito del sitio:
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

## Para eliminar todos los valores de configuración de los servicios web que permiten la autenticación de certificados:

  - El comando siguiente quita todos los valores de seguridad de los servicios web que permiten el uso de la autenticación de certificados:
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

Para más información, consulte [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsWebServiceConfiguration).

## Vea también

#### Otros recursos

[Configurar seguridad en el panel de control de Lync Server 2013](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)

