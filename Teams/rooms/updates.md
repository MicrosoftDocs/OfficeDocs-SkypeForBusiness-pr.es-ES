---
title: Administrar actualizaciones de Windows para salas de Microsoft Teams
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
description: El administrador puede obtener información sobre cómo administrar actualizaciones de Windows y actualizaciones de características de Windows para salas de Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7bb233ceedadeaf9c7f14ddf831bd9d324d9211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117368"
---
# <a name="manage-windows-updates"></a>Administrar actualizaciones de Windows

Microsoft Teams Rooms se ejecuta en Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) y recibe las mismas actualizaciones de Windows y compilaciones del sistema operativo que un equipo de escritorio estándar.

Las actualizaciones de Windows se pueden administrar como se describe en las secciones siguientes:

## <a name="hands-off-approach"></a>Enfoque de manos libres 

- De forma predeterminada, las actualizaciones se descargan directamente desde Actualizaciones de Windows automáticamente e se instalan durante fuera de horario.
- Las actualizaciones no aplazables se instalan automáticamente el día uno de la versión.
- Actualizaciones de calidad y controladores descargan e instalan el día uno automáticamente.
- Actualizaciones de características. Vea las notas siguientes.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Actualizaciones de Windows para empresas (GPO o Intune)  

- [Descarga de Actualizaciones de Windows para empresas](/windows/deployment/update/waas-manage-updates-wufb)
- Las actualizaciones se descargan desde Windows Update o wsus, pero con retrasos configurados más allá de la fecha de lanzamiento original.
- Puede usar varias us o directivas filtradas para crear "anillos" de implementación donde los administradores pueden especificar qué dispositivos instalan actualizaciones de calidad en primer lugar y cuáles se instalan más adelante. La confiabilidad y el rendimiento se pueden probar en un subconjunto de sistemas antes de implementar actualizaciones en toda la implementación sin la sobrecarga de administración de actualizaciones de Windows en El Administrador de configuración.
- Las actualizaciones de WSUS y Windows para empresas se pueden configurar al [mismo](/windows/deployment/update/waas-integrate-wufb) tiempo si desea tanto la administración de ancho de banda como el control que proporciona Actualizaciones de Windows para empresas.
- Actualizaciones de características. Vea las notas siguientes.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [Descarga de WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Al igual que Windows Update para empresas, pero con la opción adicional de dirigir KB específicas dentro de cada "anillo" o de toda la implementación. Cada actualización se puede implementar y probar individualmente a su voluntad, en lugar de depender solo de un retraso.
- Actualizaciones de características. Vea las notas siguientes.

### <a name="feature-updates"></a>Actualizaciones de características

A diferencia de las actualizaciones de calidad y no aplazables, las "actualizaciones de características" de Windows 10 (versiones principales del sistema operativo) solo se instalarán después de que Microsoft compruebe y valide una funcionalidad de actualizaciones determinada con Salas de Microsoft Teams. Incluso si la actualización se publica en el Canal de Semi-Annual (o Dirigido si tiene sistemas establecidos en ese canal para realizar pruebas) o se inserta manualmente, un dispositivo de Microsoft Room Systems no permitirá la instalación de la actualización sin probar.

Salas de Microsoft Teams funciona "de forma automática" con un enfoque de entrega y no instalará Windows Update ni reiniciará automáticamente un dispositivo para Windows Update. Los sistemas descargan una actualización y esperan al siguiente reinicio para instalarla. A menos que alguien lo reinicie manualmente, la instalación solo se produce en el reinicio automático por la noche. Las actualizaciones de Windows deben ser transparentes en la sala y el funcionamiento normal nunca debe interrumpirse con actualizaciones de Windows.

Si elige unirse a un dominio de dispositivos, use Microsoft Endpoint Configuration Manager o WSUS. Preste especial atención a las directivas o acciones que den como resultado una actualización del dispositivo o un reinicio forzoso durante el horario laboral. Los sistemas de la implementación no deben reiniciarse durante el uso o alertar sobre actualizaciones de Windows a través de la interfaz de usuario durante el horario de uso, revise la configuración si se produce ese comportamiento.