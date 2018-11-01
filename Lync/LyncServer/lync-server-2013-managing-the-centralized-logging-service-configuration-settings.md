---
title: "Opciones de configuración del servicio de registro centralizado con PowerShell"
TOCTitle: "Gest. des par. de conf. du serv. de journ. centralisée à l’aide de PowerShell"
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49889816
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administración de las opciones de configuración del servicio de registro centralizado con PowerShell

 

_**Última modificación del tema:** 2012-11-01_

El control y la configuración de Servicio de registro centralizado se manejan mediante las opciones de configuración y los parámetros que se crean y usan con el Controlador de Servicio de registro centralizado (CLSController) para enviar comandos al Agente de Servicio de registro centralizado (CLSAgent) de cada equipo en particular. El agente procesa los comandos que le envían y (en el caso del comando Start) usa la configuración de los escenarios, los proveedores, el tamaño del registro, la duración del seguimiento y los indicadores para comenzar a recopilar registros de seguimiento de acuerdo con la información de configuración facilitada.

> [!IMPORTANT]  
> No todos los cmdlets de Windows PowerShell que se muestran para Servicio de registro centralizado están pensados para ser usados con implementaciones locales de Lync Server 2013. Aunque parezcan que funcionan, los siguientes cmdlets no están diseñados para funcionar con implementaciones locales de Lync Server 2013:
> <ul>
> <li><p><strong>Cmdlets de CsClsRegion:</strong> <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsRegion">Get-CsClsRegion</a>, <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsRegion">Set-CsClsRegion</a>, <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsRegion">New-CsClsRegion</a> y <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsRegion">Remove-CsClsRegion</a>.</p></li>
> <li><p><strong>Cmdlets de CsClsSearchTerm:</strong> <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsSearchTerm">Get-CsClsSearchTerm</a> y <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsSearchTerm">Set-CsClsSearchTerm</a>.</p></li>
> <li><p><strong>Cmdlets de CsClsSecurityGroup:</strong> <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsSecurityGroup">Get-CsClsSecurityGroup</a>, <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsSecurityGroup">Set-CsClsSecurityGroup</a>, <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsSecurityGroup">New-CsClsSecurityGroup</a> y <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsSecurityGroup">Remove-CsClsSecurityGroup</a>.</p></li>
> </ul>
> La configuración definida en estos cmdlets no obstaculizará las operaciones ni provocará un mal comportamiento, pero está diseñada para ser usada con Microsoft Office 365 y no ofrecerá los resultados esperados en implementaciones locales. Lo cual no significa que estos cmdlets no sirvan para las implementaciones locales, sino que lo cierto es que tienen un uso más avanzado que no se aborda en esta documentación.


## En esta sección

En los temas de esta sección se definen las opciones de configuración, los parámetros y los ajustes de Servicio de registro centralizado. Encontrará información sobre cómo configurar Servicio de registro centralizado, cómo recuperar las opciones de configuración, la creación de escenarios, la gestión de grupos de seguridad para Servicio de registro centralizado, la búsqueda y otros temas en los temas siguientes.

  - [Administración de la configuración del servicio de registro centralizado en el ámbito de equipo, sitio y global](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [Configurar proveedores para el servicio de registro centralizado](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [Configuración de escenarios para el servicio de registro centralizado](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

## Vea también

#### Conceptos

[Descripción general del servicio de registro centralizado](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Cmdlets de registro centralizado](https://docs.microsoft.com/en-us/powershell/module/skype/)

