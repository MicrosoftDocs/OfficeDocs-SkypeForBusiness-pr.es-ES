---
title: "Suppr. des paramètres de configuration d’un serveur d’inscriptions existant"
TOCTitle: "Suppr. des paramètres de configuration d’un serveur d’inscriptions existant"
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48276343
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminación de opciones de configuración existentes del registrador

 

_**Última modificación del tema:** 2013-02-23_

Siga estos pasos para eliminar un registrador.

## Para eliminar un registrador

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Seguridad** y luego en **Registrador**.

4.  En la página **Registrador**, en el campo de búsqueda, escriba el nombre completo o parcial del registrador que desea eliminar.

5.  En la lista, haga clic en el registrador que desee, haga clic en **Editar** y luego en **Eliminar**.

6.  Haga clic en **Aceptar**.

## Quitar las opciones de configuración del registrador con los cmdlets del Shell de administración de Lync Server

También puede eliminar las opciones de configuración del registrador con el Shell de administración de Lync Server y el cmdlet **Remove-CsProxyConfiguration**. Puede ejecutar este cmdlet desde el Shell de administración de Lync Server 2013 desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para quitar un conjunto específico de opciones de configuración de seguridad del registrador

  - El siguiente comando quita las opciones de configuración de seguridad del registrador aplicadas al servidor perimetral atl-edge-011.litwareinc.com:
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

## Para quitar todas las opciones de configuración de seguridad del registrador aplicadas al ámbito de sitio

  - El siguiente comando quita todas las opciones de configuración de seguridad del registrador aplicadas al servicio del registrador:
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

## Para quitar todas las opciones de configuración de seguridad del registrador que permiten la autenticación NTLM

  - El siguiente comando elimina todas las opciones de configuración de seguridad del registrador que permiten el uso de NTLM para la autenticación de cliente:
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

Para más información, vea [Remove-CsProxyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsProxyConfiguration).

