---
title: Lista de comprobación de la primera ejecución del Panel de control de Skype Empresarial Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
description: Bienvenido a la Skype para el Panel de Control de servidor empresarial, la interfaz de usuario basada en web para la administración y la administración de Skype para Business Server. Puede usar el Panel de control para acometer los tipos de tareas administrativas que se realizaban usando Microsoft Management Console en versiones anteriores.
ms.openlocfilehash: 510838c2924f32ca532bfc075cc2c457f12cf3de
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200733"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Lista de comprobación de la primera ejecución del Panel de control de Skype Empresarial Server

Bienvenido a la Skype para el Panel de Control de servidor empresarial, la interfaz de usuario basada en web para la administración y la administración de Skype para Business Server. Puede usar el Panel de control para acometer los tipos de tareas administrativas que se realizaban usando Microsoft Management Console en versiones anteriores.

Hay un número de tareas importantes que se recomienda encarecidamente que realizar después de haber implementado Skype para Business Server. Algunas de estas tareas son pasos de configuración inicial que puede haber realizado ya durante la implementación, mientras que otras son ajustes o modificaciones de las configuraciones que se han definido durante la implementación o la configuración predeterminada. Otras tareas que se describen en este tema validan las configuraciones que ha realizado durante el proceso de implementación.

> [!NOTE]
> Antes de realizar las tareas recogidas en la siguiente tabla, compruebe que ha iniciado sesión con los derechos de usuario, permisos y roles correctos, tal y como se describe en la sección sobre roles y ámbito del tema [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx).

## <a name="first-run-checklist"></a>Lista de comprobación de la primera ejecución

Se recomienda encarecidamente que revise las tareas que se hace referencia en este tema y, a continuación, realice los procedimientos apropiados para la implementación de Lync Server en su organización.

|**Tarea**|**Grupo del Panel de control**|**Documentación**|
|:-----|:-----|:-----|
|Comprobar que los servicios instalados en la topología se ejecutan como deben.  <br/> |**Topología** <br/> |[View Details About a Service](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|Permitir que los usuarios de Skype para Business Server. De forma opcional y, si la migración desde una versión anterior, mover los usuarios a Skype para Business Server.  <br/> |**Usuarios** <br/> |[Managing Users](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|Si ha implementado o desea implementar Telefonía IP empresarial, configure una conexión de enlace troncal SIP para habilitar la conectividad con la red telefónica conmutada (RTC).  <br/> |**Enrutamiento de voz** <br/> |[Configuring Trunks and Translation Rules](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|Si ha implementado Telefonía IP empresarial, compruebe la configuración de enrutamiento de Telefonía IP empresarial.  <br/> |**Enrutamiento de voz** <br/> |[Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|Si ha implementado el servidor de archivado, compruebe que la configuración y las directivas de archivado cumplen los requisitos de conformidad de la organización.  <br/> |**Supervisión y archivado** <br/> |[Managing Archiving](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|Si ha implementado el servidor de supervisión, mire los informes del servidor de supervisión para ver la información de uso y diagnóstico.  <br/> |**Principal** <br/> |[Administrar el mantenimiento y la supervisión en Skype Empresarial Server 2015](../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


