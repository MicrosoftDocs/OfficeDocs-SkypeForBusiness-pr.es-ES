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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.assetid: ''
description: El administrador puede obtener información sobre cómo administrar Windows actualizaciones y Windows de características de Salas de Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c904db6b168280619b203a1327d6477736077efe
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015010"
---
# <a name="manage-windows-updates"></a>Administrar Windows actualizaciones

Salas de Microsoft Teams se ejecuta en Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) y recibe las mismas Windows actualizaciones y compilaciones del sistema operativo que un equipo de escritorio estándar.

Windows las actualizaciones se pueden administrar como se describe en las secciones siguientes:

## <a name="hands-off-approach"></a>Enfoque de manos libres 

- De forma predeterminada, las actualizaciones se descargan directamente desde Windows actualizaciones automáticamente e se instalan en horas no trabajadas.
- Las actualizaciones no aplazables se instalan automáticamente el día uno de la versión.
- Actualizaciones de calidad y controladores descargan e instalan automáticamente el día uno.
- Actualizaciones de características. Vea las notas siguientes.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows actualizaciones para empresas (GPO o Intune)  

- [Windows actualizaciones para empresas](/windows/deployment/update/waas-manage-updates-wufb)
- Las actualizaciones se descargan desde Windows o desde Windows Server Update Services (WSUS), pero con retrasos configurados más allá de la fecha de lanzamiento original.
- Puede usar varias us o directivas filtradas para crear "anillos" de implementación donde los administradores pueden especificar qué dispositivos Salas de Teams instalan actualizaciones de calidad primero y cuáles se instalan más adelante. La confiabilidad y el rendimiento se pueden probar en un subconjunto de dispositivos antes de implementar actualizaciones en toda la implementación sin la sobrecarga de administración de Windows actualizaciones en Configuration Manager.
- Wsus y Windows actualizaciones para empresas [](/windows/deployment/update/waas-integrate-wufb) se pueden configurar al mismo tiempo si desea tanto la administración de ancho de banda como el control Windows actualizaciones para empresas.
- Actualizaciones de características. Vea las notas siguientes.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [Descarga de WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Al igual que Windows actualización para empresas, pero con la opción adicional de dirigir KB específicos dentro de cada "anillo" o toda la implementación. Cada actualización se puede implementar y probar individualmente a su voluntad, en lugar de depender solo de un retraso.
- Actualizaciones de características. Vea las notas siguientes.

### <a name="feature-updates"></a>Actualizaciones de características

A diferencia de las actualizaciones de calidad y no aplazables, Windows 10 las "actualizaciones de características" (versiones principales del sistema operativo) solo se instalarán después de que Microsoft compruebe y valide una funcionalidad de actualizaciones determinada con Salas de Microsoft Teams. Incluso si la actualización se publica en el Canal de Semi-Annual (o Dirigido si tiene sistemas establecidos en ese canal para pruebas) o se inserta manualmente, Salas de Microsoft Teams no permitirá que se instale la actualización sin probar.

Salas de Microsoft Teams funciones "de fuera de la caja" con un enfoque práctico. Salas de Teams descargar una actualización y esperar al siguiente reinicio para instalarla. A menos que alguien lo reinicie manualmente, la instalación solo se produce en el reinicio automático por la noche. Windows actualizaciones deben ser transparentes en la sala y el funcionamiento normal nunca debe interrumpirse con Windows actualizaciones.

Si elige unirse a un dominio de dispositivos, puede usar Microsoft Endpoint Configuration Manager o WSUS. Preste especial atención a las directivas o acciones que den como resultado una actualización del dispositivo o un reinicio forzoso durante el horario laboral. Salas de Teams reiniciar durante el uso o alertar sobre Windows actualizaciones a través de la interfaz de usuario durante el horario de uso. Revise la configuración si se produce ese comportamiento.
