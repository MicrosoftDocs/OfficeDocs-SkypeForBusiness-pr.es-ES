---
title: Administrar windows Novedades para Salas de Microsoft Teams
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
- Teams_ITAdmin_Rooms
ms.assetid: ''
description: Administración puede obtener información sobre cómo administrar las actualizaciones de características de Windows Novedades y Windows para Salas de Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1df5521bdfafe38854a0b6a3821e86218ce95a0b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272185"
---
# <a name="manage-windows-updates"></a>Administrar windows Novedades

Salas de Microsoft Teams se ejecuta en Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) y recibe las mismas compilaciones de Windows Novedades y so que un equipo de escritorio estándar.

Los Novedades de Windows se pueden administrar como se describe en las siguientes secciones:

## <a name="hands-off-approach"></a>Enfoque de manos fuera 

- De manera predeterminada, las actualizaciones se descargan directamente desde Windows Novedades automáticamente y se instalan durante las horas sin conexión.
- Los Novedades no aplazables instalan automáticamente el primer día del lanzamiento.
- Los Novedades de calidad y los controladores se descargan e instalan automáticamente el primer día.
- Novedades de características. Vea las notas siguientes.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows Novedades para empresas (GPO o Intune)  

- Descarga [de Windows Novedades para empresas](/windows/deployment/update/waas-manage-updates-wufb)
- Novedades se descargan de Windows Update o de tu Windows Server Update Services (WSUS), pero con retrasos configurados más allá de la fecha de lanzamiento original.
- Puede usar varias UO o directivas filtradas para crear "anillos" de implementación, donde los administradores pueden especificar qué dispositivos Salas de Teams instalan primero Novedades de calidad y cuáles instalar más adelante. La confiabilidad y el rendimiento se pueden probar en un subconjunto de dispositivos antes de implementar actualizaciones en toda la implementación sin la sobrecarga de administrar windows Novedades en Configuration Manager.
- WSUS y Windows Novedades para empresas se pueden [configurar al mismo tiempo](/windows/deployment/update/waas-integrate-wufb) si desea la administración del ancho de banda y el control que proporciona Windows Novedades para empresas.
- Actualizaciones de características. Vea las notas siguientes.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- Descarga [de WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- De forma muy similar a Windows Update para empresas, pero con la opción adicional de dirigirse a kb específicos dentro de cada "anillo" o toda la implementación. Cada actualización se puede implementar y probar individualmente a voluntad, en lugar de basarse en un solo retraso.
- Actualizaciones de características. Vea las notas siguientes.

### <a name="feature-updates"></a>Actualizaciones de características

A diferencia de las actualizaciones de calidad y no aplazables, Windows 10 "Novedades de características" (versiones principales del sistema operativo) solo se instalarán después de que Microsoft pruebe y valide una funcionalidad de actualizaciones determinada con Salas de Microsoft Teams. Incluso si la actualización se publica en el Canal de Semi-Annual (o Dirigido si tiene sistemas configurados en ese canal para realizar pruebas) o se insertan manualmente, Salas de Microsoft Teams no permitirá la instalación de la actualización no probada.

Salas de Microsoft Teams funciones "predefinidas" con un enfoque de manos fuera. Salas de Teams descargar una actualización y espera a que se reinicie para instalarla. A menos que alguien lo reinicie manualmente, la instalación solo se realiza en el reinicio automático por la noche. Windows Novedades debe ser transparente en la sala y Windows Novedades nunca debe interrumpir el funcionamiento normal.

Si elige unirse a dispositivos de unión a un dominio, puede usar el punto de conexión de Microsoft Configuration Manager o WSUS. Presta especial atención a las directivas o acciones que dan como resultado una actualización del dispositivo o reinicio forzado durante el horario comercial. Salas de Teams no debería reiniciarse durante el uso o alertar sobre Windows Novedades sobre la interfaz de usuario durante las horas de uso. Revise la configuración si se produce ese comportamiento.
