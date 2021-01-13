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
ms.openlocfilehash: 4f7fd6d49c78b229a3909e88689423dc95ce2c48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832880"
---
# <a name="manage-windows-updates"></a>Administrar actualizaciones de Windows

Salas de Microsoft Teams se ejecuta en Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) y recibe las mismas actualizaciones de Windows y compilaciones del sistema operativo que un escritorio estándar.

Las actualizaciones de Windows se pueden administrar de varias maneras diferentes:

## <a name="hands-off-approach"></a>Enfoque de entrega 
- Las actualizaciones se pueden descargar directamente desde actualizaciones de Windows automáticamente e instalarse en horario no comercial. Si no se realiza ningún cambio en la configuración, este es el estado predeterminado.
- Las actualizaciones no aplazables se instalarán automáticamente el primer día de la versión. 
- Los controladores y actualizaciones de calidad se descargarán e instalarán el día uno automáticamente. 
- Actualizaciones de características. Vea las notas adicionales a continuación. 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Actualizaciones de Windows para empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO o Intune)   
- Las actualizaciones se descargan de WU o wsus, pero con retrasos configurados más allá de la fecha de lanzamiento original de KB. 
- En combinación con varias ou o directivas filtradas, esto permite la creación de "anillos" de implementación, donde los administradores pueden especificar qué dispositivos instalan primero las actualizaciones de calidad y cuáles se instalarán más adelante. Esto permite realizar pruebas de confiabilidad y rendimiento en un subconjunto de sistemas antes de implementar actualizaciones en toda la implementación sin la sobrecarga de administración de actualizaciones de Windows en Microsoft Endpoint Configuration Manager, por ejemplo.
- Las actualizaciones de WSUS y Windows para empresas se pueden configurar al [mismo](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) tiempo si quieres tanto la administración de ancho de banda como el control que proporciona Windows Updates para empresas.
- Actualizaciones de características. Vea las notas adicionales a continuación.

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Es muy parecido a Windows Update para empresas, pero con la opción adicional de dirigirse a KB específicos dentro de cada "anillo" o toda la implementación. Cada actualización se puede implementar y probar individualmente a su voluntad, en lugar de basarse solo en un retraso. 
- Actualizaciones de características. Vea las notas adicionales a continuación.


### <a name="feature-updates"></a>Actualizaciones de características

A diferencia de las actualizaciones de calidad y no aplazables, las "actualizaciones de características" de Windows 10 (versiones principales del sistema operativo) solo se instalarán después de que Microsoft compruebe y valide una funcionalidad de actualizaciones determinada con salas de Microsoft Teams. Incluso si se publica en el canal de Semi-Annual (o dirigido si tiene sistemas establecidos en ese canal para pruebas) o incluso presionado manualmente por sus propios intentos o configuraciones, no permitirá la instalación hasta que se quite el bloque en nuestro extremo.

La sala de Microsoft Teams "lista para usar", con el enfoque de entrega, no instalará Windows Update ni reiniciará un dispositivo automáticamente debido a una actualización de Windows. Sin embargo, los sistemas pueden descargar una actualización y esperar al siguiente reinicio para instalarla. A menos que alguien lo reinicie manualmente, la instalación debe producirse en el reinicio automático por la noche. Las actualizaciones de Windows deben ser transparentes en la sala, la interfaz de usuario nunca debe ser interrumpida por actualizaciones de Windows.

Si decides unirte a un dominio, usa Microsoft Endpoint Configuration Manager o WSUS y presta especial atención a las directivas o acciones que pueden provocar que el dispositivo instale una actualización o fuer un reinicio durante el horario comercial. Si tienes sistemas en el reinicio de la implementación durante el uso o alertas sobre actualizaciones de Windows a través de la interfaz de usuario, querrás buscar en la configuración.
