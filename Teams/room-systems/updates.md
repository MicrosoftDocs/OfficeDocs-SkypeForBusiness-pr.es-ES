---
title: Administrar actualizaciones de Windows para salas de Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Administrar actualizaciones de Windows para salas de Microsoft Teams
ms.openlocfilehash: 5f0942efc1b503589412a1de6852d83e42a3b03e
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675424"
---
# <a name="manage-windows-updates"></a>Administrar actualizaciones de Windows

Salas de Microsoft Teams se ejecuta en Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) y recibe las mismas actualizaciones de Windows y OS que un equipo de escritorio estándar.

Las actualizaciones de Windows se pueden administrar como se describe en las siguientes secciones:

## <a name="hands-off-approach"></a>Enfoque de manos libres 

- De forma predeterminada, las actualizaciones se descargan directamente desde las actualizaciones de Windows y se instalan de forma automática fuera del horario laboral.
- Las actualizaciones no aplazables instalan el día: una de las versiones automáticamente.
- Las actualizaciones de calidad y los drivers descargan e instalan automáticamente el día.
- Actualizaciones de características. Vea las notas siguientes.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows Updates para empresas (GPO o Intune)  

- Descarga [de actualizaciones de Windows para empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- Las actualizaciones se descargan desde Windows Update o WSUS, pero con retrasos configurados más allá de la fecha de lanzamiento original.
- Puede usar varias unidades organizativas o directivas filtradas para crear "anillos" de implementación donde los administradores puedan especificar qué dispositivos instalan primero las actualizaciones de calidad y cuáles se instalarán más adelante. La confiabilidad y el rendimiento se pueden probar en un subconjunto de sistemas antes de implementar las actualizaciones en toda la implementación sin la carga de administrar las actualizaciones de Windows en SCCM.
- Las actualizaciones de WSUS y Windows para empresas pueden [configurarse al mismo tiempo](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) si quiere tanto la administración de ancho de banda como el control que ofrece Windows Updates para empresas.
- Actualizaciones de características. Vea las notas siguientes.

## <a name="wsussccm"></a>WSUS/SCCM

- Descarga de [WSUS o SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- De manera muy similar a Windows Update para empresas, pero con la opción adicional de segmentar las KB específicas dentro de cada "timbre" o toda la implementación. Cada actualización se puede implementar y probar individualmente en la misma, en lugar de confiar únicamente en un retraso.
- Actualizaciones de características. Vea las notas siguientes.

### <a name="feature-updates"></a>Actualizaciones de características

A diferencia de las actualizaciones de calidad y no aplazable, las actualizaciones de características de Windows 10 (versiones principales del sistema operativo) solo se instalarán después de que Microsoft pruebe y valide una funcionalidad de actualizaciones determinada con salas de Microsoft Teams. Aunque la actualización se publique para el canal semianual (o se destinan a los sistemas establecidos en ese canal para pruebas) o a la inserción manual, un dispositivo de Microsoft Room Systems no permitirá la instalación de la actualización no comprobada.

Salas de Microsoft Teams las funciones "preparadas" con un enfoque de manos libres y no instalarán Windows Update ni reiniciarán automáticamente un dispositivo para Windows Update. Los sistemas descargan una actualización y esperan al siguiente reinicio para instalarla. A menos que alguien lo reinicie manualmente, la instalación solo se realizará durante el reinicio automático por la noche. Las actualizaciones de Windows deberían ser transparentes en la sala, y las actualizaciones de Windows nunca deberán interrumpir el funcionamiento normal.

Si elige para unirse a un dominio, use SCCM o WSUS. Preste especial atención a las directivas o acciones que tengan como resultado la actualización de un dispositivo o el reinicio forzado durante el horario comercial. Los sistemas de la implementación no se deben reiniciar durante el uso o la alerta sobre actualizaciones de Windows a través de la interfaz de usuario durante las horas de uso, revise la configuración si ese comportamiento se produce.