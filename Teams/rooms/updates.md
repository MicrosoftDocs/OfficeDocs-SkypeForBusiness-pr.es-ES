---
title: Administrar Windows actualizaciones de Salas de Microsoft Teams
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
description: El administrador puede obtener información sobre cómo administrar Windows actualizaciones y Windows de características de Salas de Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 67144ff29077a3dec6be79b9b68efb1162d31a9069b3436b29f9ac50a4857914
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54275966"
---
# <a name="manage-windows-updates"></a>Administrar Windows actualizaciones

Salas de Microsoft Teams se ejecuta en Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) y recibe las mismas Windows actualizaciones y compilaciones del sistema operativo que un equipo de escritorio estándar.

Windows Las actualizaciones se pueden administrar como se describe en las secciones siguientes:

## <a name="hands-off-approach"></a>Enfoque de manos libres 

- De forma predeterminada, las actualizaciones se descargan directamente desde Windows actualizaciones automáticamente e se instalan en horas no trabajadas.
- Las actualizaciones no aplazables se instalan automáticamente el día uno de la versión.
- Actualizaciones de calidad y controladores descargan e instalan el día uno automáticamente.
- Actualizaciones de características. Vea las notas siguientes.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows Actualizaciones para empresas (GPO o Intune)  

- [Windows actualizaciones para empresas](/windows/deployment/update/waas-manage-updates-wufb)
- Las actualizaciones se descargan desde Windows o wsus, pero con retrasos configurados más allá de la fecha de lanzamiento original.
- Puede usar varias us o directivas filtradas para crear "anillos" de implementación donde los administradores pueden especificar qué dispositivos instalan actualizaciones de calidad en primer lugar y cuáles se instalan más adelante. La confiabilidad y el rendimiento se pueden probar en un subconjunto de sistemas antes de implementar actualizaciones en toda la implementación sin la sobrecarga de administración de Windows actualizaciones en Configuration Manager.
- Wsus y Windows actualizaciones para empresas [](/windows/deployment/update/waas-integrate-wufb) se pueden configurar al mismo tiempo si desea tanto la administración de ancho de banda como el control Windows actualizaciones para empresas.
- Actualizaciones de características. Vea las notas siguientes.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [Descarga de WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Al igual que Windows actualización para empresas, pero con la opción adicional de dirigir KB específicos dentro de cada "anillo" o toda la implementación. Cada actualización se puede implementar y probar individualmente a su voluntad, en lugar de depender solo de un retraso.
- Actualizaciones de características. Vea las notas siguientes.

### <a name="feature-updates"></a>Actualizaciones de características

A diferencia de las actualizaciones de calidad y no aplazables, Windows 10 las "actualizaciones de características" (versiones principales del sistema operativo) solo se instalarán después de que Microsoft compruebe y valide una funcionalidad de actualizaciones determinada con Salas de Microsoft Teams. Incluso si la actualización se publica en el Canal de Semi-Annual (o Dirigido si tiene sistemas establecidos en ese canal para realizar pruebas) o se inserta manualmente, un dispositivo de Microsoft Room Systems no permitirá la instalación de la actualización sin probar.

Salas de Microsoft Teams funciones "lista para su uso" con un enfoque de entrega, y no instalará una actualización de Windows ni reiniciará automáticamente un dispositivo para una actualización Windows usuario. Los sistemas descargan una actualización y esperan al siguiente reinicio para instalarla. A menos que alguien lo reinicie manualmente, la instalación solo se produce en el reinicio automático por la noche. Windows Las actualizaciones deben ser transparentes en el salón y el funcionamiento normal nunca debe interrumpirse con Windows actualizaciones.

Si elige unirse a un dominio de dispositivos, use Microsoft Endpoint Configuration Manager o WSUS. Preste especial atención a las directivas o acciones que den como resultado una actualización del dispositivo o un reinicio forzoso durante el horario laboral. Los sistemas de la implementación no deben reiniciarse durante el uso o alertar sobre Windows Actualizaciones a través de la interfaz de usuario durante el horario de uso, revise la configuración si se produce ese comportamiento.