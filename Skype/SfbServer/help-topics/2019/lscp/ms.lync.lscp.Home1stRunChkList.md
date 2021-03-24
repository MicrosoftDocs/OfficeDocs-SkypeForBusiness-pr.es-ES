---
title: Lista de comprobación de la primera ejecución del Panel de control de Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
ROBOTS: NOINDEX, NOFOLLOW
description: Bienvenido al Panel de control de Skype Empresarial Server, la interfaz de usuario basada en web para la administración y administración de Skype Empresarial Server. Puede usar el panel de control para realizar los tipos de tareas administrativas que se realizaron con Microsoft Management Console en versiones anteriores.
ms.openlocfilehash: 3e8fee53c37079c46862e05f246d984c621b57ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100446"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Lista de comprobación de la primera ejecución del Panel de control de Skype Empresarial Server

Bienvenido al Panel de control de Skype Empresarial Server, la interfaz de usuario basada en web para la administración y administración de Skype Empresarial Server. Puede usar el panel de control para realizar los tipos de tareas administrativas que se realizaron con Microsoft Management Console en versiones anteriores.

Hay una serie de tareas importantes que le recomendamos encarecidamente que realice después de implementar Skype Empresarial Server. Algunas de estas tareas son pasos de configuración inicial que puede haber realizado ya durante la implementación, mientras que otras son ajustes o modificaciones de las configuraciones que se han definido durante la implementación o la configuración predeterminada. Otras tareas que se describen en este tema validan las configuraciones que ha realizado durante el proceso de implementación.

> [!NOTE]
> Antes de realizar las tareas de la tabla siguiente, asegúrese de iniciar sesión con los derechos de usuario, permisos y roles correctos, tal como se describe en la sección "Roles y ámbito" del tema Control de acceso basado en [roles.](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)

## <a name="first-run-checklist"></a>Lista de comprobación de la primera ejecución

Se recomienda encarecidamente revisar las tareas a las que se hace referencia en este tema y, a continuación, realizar los procedimientos adecuados para la implementación en la organización.

|**Task**|**Grupo panel de control**|**Documentación**|
|:-----|:-----|:-----|
|Comprobar que los servicios instalados en su topología se ejecutan como deberían.  <br/> |**Topología** <br/> |[Ver detalles sobre un servicio](/previous-versions/office/lync-server-2013/lync-server-2013-view-details-about-a-service) <br/> |
|Habilitar usuarios para Skype Empresarial Server. Opcionalmente y, si se migra desde una versión anterior, mueva usuarios a Skype Empresarial Server.  <br/> |**Usuarios** <br/> |[Administración de usuarios](/previous-versions/office/lync-server-2013/lync-server-2013-user-accounts-enabled-for-lync-server) <br/> |
|Si ha implementado o desea implementar Enterprise Voice, configure una conexión de enlace troncal SIP para habilitar la conectividad con la red telefónica conmutada (RTC).  <br/> |**Enrutamiento de voz** <br/> |[Configuración de troncos y reglas de traducción](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-trunks) <br/> |
|Si ha implementado Enterprise Voice, compruebe la configuración de enrutamiento de Enterprise Voice.  <br/> |**Enrutamiento de voz** <br/> |[Probar enrutamiento de voz](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing) <br/> |
|Si ha implementado el servidor de archivado, compruebe que la configuración y las directivas de archivado cumplen los requisitos de conformidad de su organización.  <br/> |**Supervisión y archivado** <br/> |[Administración del archivado](/previous-versions/office/lync-server-2013/lync-server-2013-managing-archiving) <br/> |
|Si ha implementado el servidor de supervisión, consulte los informes del servidor de supervisión para ver la información de uso y diagnóstico.  <br/> |**Inicio** <br/> |[Administrar el estado y la supervisión en Skype Empresarial Server](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |