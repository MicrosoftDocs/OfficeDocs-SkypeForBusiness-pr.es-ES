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
ms.openlocfilehash: fdd6aeefb6c4914dec54673f426c95c4028388ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836630"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Lista de comprobación de la primera ejecución del Panel de control de Skype Empresarial Server

Bienvenido al Panel de control de Skype Empresarial Server, la interfaz de usuario basada en web para la administración y administración de Skype Empresarial Server. Puede usar el panel de control para realizar los tipos de tareas administrativas que se realizaron con Microsoft Management Console en versiones anteriores.

Hay una serie de tareas importantes que le recomendamos encarecidamente que realice después de implementar Skype Empresarial Server. Algunas de estas tareas son pasos de configuración inicial que puede haber realizado ya durante la implementación, mientras que otras son ajustes o modificaciones de las configuraciones que se han definido durante la implementación o la configuración predeterminada. Otras tareas que se describen en este tema validan las configuraciones que ha realizado durante el proceso de implementación.

> [!NOTE]
> Antes de realizar las tareas de la tabla siguiente, asegúrese de iniciar sesión con los derechos de usuario, permisos y roles correctos, tal como se describe en la sección "Roles y ámbito" del tema Control de acceso basado en [roles.](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)

## <a name="first-run-checklist"></a>Lista de comprobación de la primera ejecución

Se recomienda encarecidamente revisar las tareas a las que se hace referencia en este tema y, a continuación, realizar los procedimientos adecuados para la implementación en la organización.

|**Task**|**Grupo panel de control**|**Documentación**|
|:-----|:-----|:-----|
|Comprobar que los servicios instalados en su topología se ejecutan como deberían.  <br/> |**Topología** <br/> |[Ver detalles sobre un servicio](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|Habilitar usuarios para Skype Empresarial Server. Opcionalmente y, si realiza la migración desde una versión anterior, mueva usuarios a Skype Empresarial Server.  <br/> |**Usuarios** <br/> |[Administración de usuarios](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|Si ha implementado o desea implementar Enterprise Voice, configure una conexión de enlace troncal SIP para habilitar la conectividad con la red telefónica conmutada (RTC).  <br/> |**Enrutamiento de voz** <br/> |[Configuración de troncos y reglas de conversión](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|Si ha implementado Enterprise Voice, compruebe la configuración de enrutamiento de Enterprise Voice.  <br/> |**Enrutamiento de voz** <br/> |[Probar enrutamiento de voz](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|Si ha implementado el servidor de archivado, compruebe que la configuración y las directivas de archivado cumplen los requisitos de conformidad de su organización.  <br/> |**Supervisión y archivado** <br/> |[Administración del archivado](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|Si ha implementado el servidor de supervisión, consulte los informes del servidor de supervisión para ver la información de uso y diagnóstico.  <br/> |**Inicio** <br/> |[Administrar el estado y la supervisión en Skype Empresarial Server](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


