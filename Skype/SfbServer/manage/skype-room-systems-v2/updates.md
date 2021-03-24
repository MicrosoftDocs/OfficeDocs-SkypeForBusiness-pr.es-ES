---
title: Administrar actualizaciones de Windows para salas de Microsoft Teams
ms.author: v-cichur
author: cichur
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Administrar actualizaciones de Windows para salas de Microsoft Teams
ms.openlocfilehash: cb3007acd31f84cedb8996f440b9634f0551f638
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103206"
---
# <a name="manage-windows-updates"></a>Administrar actualizaciones de Windows

Microsoft Teams Rooms se ejecuta en Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) y recibe las mismas actualizaciones de Windows y compilaciones del sistema operativo que un escritorio estándar.

Las actualizaciones de Windows se pueden administrar de varias maneras diferentes:

## <a name="hands-off-approach"></a>Enfoque de entrega 
- Las actualizaciones se pueden descargar directamente desde Actualizaciones de Windows de forma automática e instalarse durante el horario de intesa. Si no se realiza ningún cambio en la configuración, este es el estado predeterminado.
- Las actualizaciones no aplazables se instalarán automáticamente el primer día de la versión. 
- Los controladores y actualizaciones de calidad se descargarán e instalarán el primer día automáticamente. 
- Actualizaciones de características. Vea las notas adicionales a continuación. 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Actualizaciones de Windows para empresas](/windows/deployment/update/waas-manage-updates-wufb) (GPO o Intune)   
- Las actualizaciones se descargan desde WU o wsus, pero con retrasos configurados más allá de la fecha de lanzamiento original de KB. 
- Combinado con varias directivas de OU o filtradas, esto permite la creación de "anillos" de implementación, donde los administradores pueden especificar qué dispositivos instalan las actualizaciones de calidad primero y cuáles se instalarán más adelante. Esto permite realizar pruebas de confiabilidad y rendimiento en un subconjunto de sistemas antes de implementar actualizaciones en toda la implementación sin la sobrecarga de administrar actualizaciones de Windows en Microsoft Endpoint Configuration Manager, por ejemplo.
- Las actualizaciones de WSUS y Windows para empresas se pueden configurar al [mismo](/windows/deployment/update/waas-integrate-wufb) tiempo si quieres tanto la administración de ancho de banda como el control que windows updates para empresas proporciona.
- Actualizaciones de características. Vea las notas adicionales a continuación.

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Al igual que Windows Update para empresas, pero con la opción adicional de seleccionar KB específicos en cada "anillo" o en toda la implementación. Cada actualización se puede implementar y probar individualmente a voluntad, en lugar de depender solo de un retraso. 
- Actualizaciones de características. Vea las notas adicionales a continuación.


### <a name="feature-updates"></a>Actualizaciones de características

A diferencia de las actualizaciones de calidad y no aplazables, las "actualizaciones de características" de Windows 10 (principales versiones del sistema operativo) solo se instalarán después de que Microsoft compruebe y valide una funcionalidad determinada de actualizaciones con salas de Microsoft Teams. Incluso si se libera en el canal de Semi-Annual (o dirigido si tiene sistemas establecidos en ese canal para pruebas) o incluso presionado manualmente por sus propios intentos o configuraciones, no permitirá la instalación hasta que se quite el bloque de nuestro extremo.

La sala de Microsoft Teams "lista para usar", mediante el método hands off, no instalará Windows Update ni reiniciará un dispositivo automáticamente debido a una actualización de Windows. Sin embargo, los sistemas pueden descargar una actualización y esperar a que se instale el siguiente reinicio. A menos que alguien lo reinicie manualmente, la instalación debe realizarse en el reinicio automático de la noche. Las actualizaciones de Windows deben ser transparentes en la sala, las actualizaciones de Windows nunca deben interrumpir la interfaz de usuario.

Si eliges unirte a un dominio, usa Microsoft Endpoint Configuration Manager o WSUS y presta especial atención a las directivas o acciones que pueden dar como resultado que el dispositivo instale una actualización o forzase un reinicio durante el horario laboral. Si tienes sistemas en el reinicio de la implementación durante el uso o alertas sobre actualizaciones de Windows a través de la interfaz de usuario, querrás ver la configuración.