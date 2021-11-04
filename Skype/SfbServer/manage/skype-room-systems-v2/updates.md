---
title: Administrar Windows actualizaciones de Salas de Microsoft Teams
ms.author: v-mahoffman
author: cichur
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: M365-voice
ms.assetid: ''
description: Administrar Windows actualizaciones de Salas de Microsoft Teams
ms.openlocfilehash: 0aab39e58472d6efac40e3b33abce66fa12b158d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740476"
---
# <a name="manage-windows-updates"></a>Administrar Windows actualizaciones

Salas de Microsoft Teams se ejecuta en Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) y recibe las mismas actualizaciones de Windows y compilaciones del sistema operativo que un escritorio estándar.

Windows Las actualizaciones se pueden administrar de varias maneras diferentes:

## <a name="hands-off-approach"></a>Enfoque de entrega 
- Las actualizaciones se pueden descargar directamente desde Windows actualizaciones automáticamente e instalarse durante las horas fuera del horario. Si no se realiza ningún cambio en la configuración, este es el estado predeterminado.
- Las actualizaciones no aplazables se instalarán automáticamente el primer día de la versión. 
- Los controladores y actualizaciones de calidad se descargarán e instalarán el primer día automáticamente. 
- Actualizaciones de características. Vea las notas adicionales a continuación. 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Windows actualizaciones para empresas](/windows/deployment/update/waas-manage-updates-wufb) (GPO o Intune)   
- Las actualizaciones se descargan desde WU o wsus, pero con retrasos configurados más allá de la fecha de lanzamiento original de KB. 
- Combinado con varias directivas de OU o filtradas, esto permite la creación de "anillos" de implementación, donde los administradores pueden especificar qué dispositivos instalan las actualizaciones de calidad primero y cuáles se instalarán más adelante. Esto permite realizar pruebas de confiabilidad y rendimiento en un subconjunto de sistemas antes de implementar actualizaciones en toda la implementación sin la sobrecarga de administrar actualizaciones Windows en Microsoft Endpoint Configuration Manager por ejemplo.
- Wsus y Windows actualizaciones para empresas [](/windows/deployment/update/waas-integrate-wufb) se pueden configurar al mismo tiempo si desea tanto la administración de ancho de banda como el control Windows actualizaciones para empresas.
- Actualizaciones de características. Vea las notas adicionales a continuación.

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Al igual que Windows actualización para empresas, pero con la opción adicional de dirigirse a KB específicos dentro de cada "anillo" o toda la implementación. Cada actualización se puede implementar y probar individualmente a voluntad, en lugar de depender solo de un retraso. 
- Actualizaciones de características. Vea las notas adicionales a continuación.


### <a name="feature-updates"></a>Actualizaciones de características

A diferencia de las actualizaciones de calidad y no aplazables, Windows 10 las "actualizaciones de características" (principales versiones del sistema operativo) solo se instalarán después de que Microsoft compruebe y valide una funcionalidad de actualizaciones determinada con Salas de Microsoft Teams. Incluso si se libera en el canal de Semi-Annual (o dirigido si tiene sistemas establecidos en ese canal para pruebas) o incluso presionado manualmente por sus propios intentos o configuraciones, no permitirá la instalación hasta que se quite el bloque de nuestro extremo.

Microsoft Teams La sala "lista para usar", con el enfoque hands off, no instalará una actualización de Windows o reiniciará un dispositivo automáticamente debido a una Windows Update. Sin embargo, los sistemas pueden descargar una actualización y esperar a que se instale el siguiente reinicio. A menos que alguien lo reinicie manualmente, la instalación debe realizarse en el reinicio automático de la noche. Windows Las actualizaciones deben ser transparentes en la sala, la interfaz de usuario nunca debe ser interrumpida por Windows actualizaciones.

Si eliges unirte a un dominio, usa Microsoft Endpoint Configuration Manager o WSUS y presta especial atención a las directivas o acciones que pueden provocar que el dispositivo instale una actualización o oblige a reiniciarlo durante el horario laboral. Si tienes sistemas en el reinicio de la implementación durante el uso o alertas sobre Windows actualizaciones a través de la interfaz de usuario, querrás buscar en la configuración.