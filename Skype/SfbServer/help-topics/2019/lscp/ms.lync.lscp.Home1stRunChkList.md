---
title: Lista de comprobación de la primera ejecución del Panel de control de Skype Empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Bienvenido al panel de control de Skype empresarial Server, la interfaz de usuario basada en web para la administración y la administración de Skype empresarial Server. Puede usar el Panel de control para acometer los tipos de tareas administrativas que se realizaban usando Microsoft Management Console en versiones anteriores.
ms.openlocfilehash: 0efd6b5730154e0f1847de6f4caf87867f977817
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797641"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Lista de comprobación de la primera ejecución del Panel de control de Skype Empresarial Server

Bienvenido al panel de control de Skype empresarial Server, la interfaz de usuario basada en web para la administración y la administración de Skype empresarial Server. Puede usar el Panel de control para acometer los tipos de tareas administrativas que se realizaban usando Microsoft Management Console en versiones anteriores.

Hay varias tareas importantes que le recomendamos encarecidamente que realice después de implementar Skype empresarial Server. Algunas de estas tareas son pasos de configuración inicial que puede haber realizado ya durante la implementación, mientras que otras son ajustes o modificaciones de las configuraciones que se han definido durante la implementación o la configuración predeterminada. Otras tareas que se describen en este tema validan las configuraciones que ha realizado durante el proceso de implementación.

> [!NOTE]
> Antes de realizar las tareas recogidas en la siguiente tabla, compruebe que ha iniciado sesión con los derechos de usuario, permisos y roles correctos, tal y como se describe en la sección sobre roles y ámbito del tema [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx).

## <a name="first-run-checklist"></a>Lista de comprobación de la primera ejecución

Le recomendamos encarecidamente que revise las tareas a las que se hace referencia en este tema y, a continuación, realice los procedimientos adecuados para la implementación de su organización.

|**Tarea**|**Grupo del Panel de control**|**Documentación**|
|:-----|:-----|:-----|
|Comprobar que los servicios instalados en la topología se ejecutan como deben.  <br/> |**Topología** <br/> |[View Details About a Service](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|Habilitar usuarios para Skype empresarial Server. De forma opcional y, si está migrando desde una versión anterior, mueva usuarios a Skype empresarial Server.  <br/> |**Usuarios** <br/> |[Managing Users](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|Si ha implementado o desea implementar Telefonía IP empresarial, configure una conexión de enlace troncal SIP para habilitar la conectividad con la red telefónica conmutada (RTC).  <br/> |**Enrutamiento de voz** <br/> |[Configuring Trunks and Translation Rules](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|Si ha implementado Telefonía IP empresarial, compruebe la configuración de enrutamiento de Telefonía IP empresarial.  <br/> |**Enrutamiento de voz** <br/> |[Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|Si ha implementado el servidor de archivado, compruebe que la configuración y las directivas de archivado cumplen los requisitos de conformidad de la organización.  <br/> |**Supervisión y archivado** <br/> |[Managing Archiving](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|Si ha implementado el servidor de supervisión, mire los informes del servidor de supervisión para ver la información de uso y diagnóstico.  <br/> |**Principal** <br/> |[Administrar el estado y la supervisión en Skype empresarial Server](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


