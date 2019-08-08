---
title: Administrar actualizaciones de Windows para salas de Microsoft Teams
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Administrar actualizaciones de Windows para salas de Microsoft Teams
ms.openlocfilehash: 434e6d28796662c1cc8904b7ad94f059d7d447b0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243283"
---
# <a name="manage-windows-updates"></a>Administrar actualizaciones de Windows

Salas de Microsoft Teams se ejecuta en Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) y recibe las mismas actualizaciones de Windows y OS que un escritorio estándar.

Las actualizaciones de Windows se pueden administrar de varias maneras diferentes:

## <a name="hands-off-approach"></a>Enfoque de manos libres 

- Las actualizaciones se pueden descargar directamente desde actualizaciones de Windows e instalarse de forma automática fuera de horas. Esta es la configuración predeterminada.
- Las actualizaciones no aplazables instalan el día: una de las versiones automáticamente.
- Las actualizaciones de calidad y los drivers descargan e instalan automáticamente el día.
- Actualizaciones de características. Vea las notas siguientes.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows Updates para empresas (GPO o Intune)  

- Descarga [de actualizaciones de Windows para empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- Las actualizaciones se descargan desde WU o WSUS, pero con retrasos configurados más allá de la fecha de lanzamiento original de KB.
- Si se usa con varias unidades organizativas o directivas filtradas, puede crear "anillos" de implementación donde los administradores puedan especificar qué dispositivos instalan primero las actualizaciones de calidad y cuáles se instalarán más adelante. Esto permite pruebas de confiabilidad y rendimiento en un subconjunto de sistemas antes de implementar las actualizaciones en toda la implementación sin la sobrecarga de administrar las actualizaciones de Windows en SCCM, por ejemplo.
- Las actualizaciones de WSUS y Windows para empresas pueden configurarse [al mismo tiempo](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) si quiere tanto la administración de ancho de banda como el control que ofrece Windows Updates para empresas.
- Actualizaciones de características. Vea las notas siguientes.

## <a name="wsussccm"></a>WSUS/SCCM

- Descarga de [WSUS o SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- De manera muy similar a Windows Update para empresas, pero con la opción adicional de segmentar las KB específicas dentro de cada "timbre" o toda la implementación. Cada actualización se puede implementar y probar individualmente en la misma, en lugar de confiar únicamente en un retraso.
- Actualizaciones de características. Vea las notas siguientes.

### <a name="feature-updates"></a>Actualizaciones de características

A diferencia de las actualizaciones de calidad y no aplazable, las actualizaciones de características de Windows 10 (versiones principales del sistema operativo) solo se instalarán después de que Microsoft pruebe y valide una funcionalidad de actualizaciones determinada con salas de Microsoft Teams. Aunque la actualización se publique para el canal semianual (o se destinan a los sistemas establecidos en ese canal para pruebas) o a la inserción manual, un dispositivo de Microsoft Room Systems no permitirá la instalación de la actualización no comprobada.

Las salas de Microsoft Teams "de forma no integrada", con el método manos libres, no instalarán Windows Update ni reiniciarán automáticamente un dispositivo para Windows Update. Los sistemas pueden descargar una actualización y esperar al siguiente reinicio para instalarlo. A menos que alguien lo reinicie manualmente, la instalación debe realizarse durante el reinicio automático nocturno. Las actualizaciones de Windows deberían ser transparentes en el salón, mientras que las actualizaciones de Windows nunca las interrumpan.

Si elige los dispositivos Unidos a un dominio, use SCCM o WSUS. Preste especial atención a las directivas o acciones que puedan dar lugar a que el dispositivo Instale una actualización o fuerce un reinicio durante el horario comercial. Los sistemas de la implementación no se deben reiniciar durante el uso o la alerta sobre actualizaciones de Windows a través de la interfaz de usuario durante las horas de uso, revise la configuración si ese comportamiento se produce.