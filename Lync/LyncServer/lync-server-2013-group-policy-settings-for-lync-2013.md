---
title: Configuración de directivas de grupo para Lync 2013
TOCTitle: Configuración de directivas de grupo para Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48275358
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de directivas de grupo para Lync 2013

 

_**Última modificación del tema:** 2016-12-08_

En versiones anteriores de Lync y Office Communicator, tenía a su disposición una plantilla administrativa Communicator.adm independiente para configurar la configuración de directivas de grupo del cliente. En Lync 2013 se incluyen nuevos archivos de plantilla administrativa (archivos .admx y .adml) junto con la plantilla administrativa de directivas de grupo de Office. La disponibilidad de los archivos .admx y .adml de Lync 2013 le permite descargar plantillas y administrar de forma centralizada la configuración de directivas de grupo de todos sus paquetes de idiomas y programas de Office. Para más información, vea “Archivos de la plantillas administrativas de Office 2013 (ADMX, ADML)” en la documentación de Office 2013 en [http://go.microsoft.com/fwlink/?linkid=267516\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=267516%26clcid=0xc0a).

## Directivas de arranque de clientes

Existen varias directivas de arranque de clientes que debe configurar antes de que los usuarios inicien sesión por primera vez en el servidor. Puesto que estas directivas entran en vigor antes de que el cliente inicie sesión y empiece a recibir la configuración de aprovisionamiento en banda del servidor, puede usar la directiva de grupo para configurarlas. Para más información, consulte [Configuración de las directivas de arranque del cliente en Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) en la documentación de implementación.

