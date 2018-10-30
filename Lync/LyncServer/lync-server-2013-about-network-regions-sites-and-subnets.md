---
title: "Lync Server 2013 : À propos des régions rés., des sites rés. et des sous-rés."
TOCTitle: Acerca de las regiones de red, sitios y subredes
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48275528
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Acerca de las regiones de red, sitios y subredes en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-24_

Las características avanzadas de Telefonía IP empresarial que se describen en esta sección comparten ciertos requisitos de configuración de regiones de red, sitios de red y subredes. Por ejemplo, las tres características avanzadas requieren que cada una de las subredes de la topología estén asociadas a un *sitio de red* específico, y cada uno de los sitios de red deben estar asociados a una *región de red* .

> [!IMPORTANT]  
> Antes de empezar la configuración de red para el control de admisión de llamadas, E9-1-1, o el desvío de medios, asegúrese de haber revisado toda la información adicional acerca de la configuración de red del tema <a href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Configuración de red para las características avanzadas de telefonía IP empresarial en Lync Server 2013</a> en la documentación referente a la planeación. Para más información sobre la configuración de red, y en particular sobre el control de admisión de llamadas, vea también <a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definición de los requisitos de la organización para el servicio de control de admisión de llamadas en Lync Server 2013</a> en la documentación referente a la planeación.



El control de admisión de llamadas y E9-1-1 tienen requisitos de configuración adicionales para los sitios de red:

  - El control de admisión de llamadas requiere que se especifique un *perfil de directiva de ancho de banda* para cada uno de los sitios restringidos con limitaciones de ancho de banda WAN. Si tiene pensado implementar el control de admisión de llamadas, deberá [Crear perfiles de directivas de ancho de banda en Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) antes de configurar los sitios de red.

  - E9-1-1 requiere que se especifique una *directiva de ubicación* para cada uno de los sitios. Si tiene pensado implementar E9-1-1, deberá [Crear directivas de ubicación en Lync Server 2013](lync-server-2013-create-location-policies.md) antes de configurar los sitios de red.

## Crear o modificar regiones de red, sitios de red y subredes

En los siguientes temas se proporcionan pasos para crear o modificar regiones de red y sitios de red, y para asociar subredes a sitios de red. Estos temas no son específicos de ninguna característica avanzada de Telefonía IP empresarial.

  - [Crear o modificar una región de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)

  - [Crear o modificar un sitio de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)

  - [Asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)

