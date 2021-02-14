---
title: Administrar las actualizaciones de Windows de salas de Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: El administrador puede obtener información sobre cómo administrar las actualizaciones de Windows y las actualizaciones de características de Windows para salas de Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e52c1fdf3bb35be6869320aa57e6f5aff5fd0773
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905312"
---
# <a name="manage-windows-updates"></a>Administrar actualizaciones de Windows

Microsoft Teams Rooms se ejecuta en Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) y recibe las mismas actualizaciones de Windows y compilaciones del sistema operativo que un equipo de escritorio estándar.

Las actualizaciones de Windows se pueden administrar como se explica en las secciones siguientes:

## <a name="hands-off-approach"></a>Enfoque de manos libres 

- De forma predeterminada, las actualizaciones se descargan directamente desde las actualizaciones de Windows y se instalan automáticamente durante las horas fuera del horario laboral.
- Las actualizaciones no aplazables se instalan el día uno de la versión automáticamente.
- Los controladores y las actualizaciones de calidad descargan e instalan el día uno automáticamente.
- Actualizaciones de características. Vea las notas siguientes.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Actualizaciones de Windows para empresas (GPO o Intune)  

- [Descarga de actualizaciones de Windows para](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) empresas
- Las actualizaciones se descargan desde Windows Update o el WSUS, pero con retrasos configurados pasados la fecha de lanzamiento original.
- Puede usar varias OUs o directivas filtradas para crear "anillos" de implementación donde los administradores pueden especificar qué dispositivos instalan actualizaciones de calidad en primer lugar y cuáles instalarán más tarde. La confiabilidad y el rendimiento se pueden probar en un subconjunto de sistemas antes de implementar actualizaciones en toda la implementación sin la sobrecarga de administrar las actualizaciones de Windows en Configuration Manager.
- Las actualizaciones de WSUS y Windows para empresas se pueden configurar al [mismo](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) tiempo si desea la administración de ancho de banda y el control que proporciona Actualizaciones de Windows para empresas.
- Actualizaciones de características. Vea las notas siguientes.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [Descarga de WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Igual que Windows Update para empresas, pero con la opción adicional de dirigirse a KB específicos dentro de cada "anillo" o toda la implementación. Cada actualización se puede implementar y probar individualmente a la vez, en lugar de basarse solo en un retraso.
- Actualizaciones de características. Vea las notas siguientes.

### <a name="feature-updates"></a>Actualizaciones de características

A diferencia de las actualizaciones de calidad y no aplazables, las "Actualizaciones de características" de Windows 10 (principales versiones de SO) solo se instalarán después de que Microsoft compruebe y valide una funcionalidad de actualizaciones determinada con Microsoft Teams Rooms. Incluso si la actualización se publica en el Canal Semi-Annual (o dirigido si tiene sistemas establecidos en ese canal para realizar pruebas) o se inserta manualmente, un dispositivo de Microsoft Room Systems no permitirá la instalación de la actualización no testada.

Salas de Microsoft Teams funciona "lista para imprimir" con un enfoque práctico y no instalará Windows Update ni reiniciará automáticamente un dispositivo para Windows Update. Los sistemas descargan una actualización y esperan al siguiente reinicio para instalarla. Unless someone reboots it manually, installation only happens at the automatic nightly reboot. Las actualizaciones de Windows deben ser transparentes en la sala y las actualizaciones de Windows no deberían interrumpir nunca el funcionamiento normal.

Si elige usar dispositivos de unión de dominios, use Microsoft Endpoint Configuration Manager o WSUS. Preste especial atención a las directivas o acciones que resulte en una actualización del dispositivo o en el reinicio forzoso durante el horario laboral. Los sistemas de la implementación no deben reiniciarse durante el uso ni estar alertas sobre las actualizaciones de Windows en la interfaz de usuario durante el horario de uso, revisa la configuración si se produce ese comportamiento.