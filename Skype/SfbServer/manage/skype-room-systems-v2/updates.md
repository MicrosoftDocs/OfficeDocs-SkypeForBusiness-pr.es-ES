---
title: Administrar las actualizaciones de Windows para salas de equipos de Microsoft
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Administrar las actualizaciones de Windows para salas de equipos de Microsoft
ms.openlocfilehash: 723ecf20fb835a3d942270e9de6d59416a9cd14a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214732"
---
# <a name="manage-windows-updates"></a>Administrar las actualizaciones de Windows

Salones de los equipos de Microsoft se ejecuta en Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) y recibe las compilaciones de actualizaciones de Windows y el sistema operativo mismas como un escritorio estándar.

Actualizaciones de Windows se puede administrar de varias formas diferentes:

## <a name="hands-off-approach"></a>Enfoque sin intervención 
- Las actualizaciones se pueden descargar directamente desde las actualizaciones de Windows automáticamente e instalar horario de trabajo habitual. Si se realiza ningún cambio en la configuración de esto es el estado predeterminado.
- Actualizaciones puede diferir no instalan automáticamente uno día del lanzamiento. 
- Actualizaciones y controladores de calidad se descargue e instale día uno automáticamente. 
- Actualizaciones de la característica. Consulte las notas adicionales que aparece a continuación. 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a>[Actualizaciones de Windows para la empresa](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO o Intune)   
- Las actualizaciones se descargan desde Windows Update o su WSUS pero con retrasos configurados más allá de la fecha de lanzamiento original de la KB. 
- Combinar con varias unidades Organizativas o filtrados de las directivas, esto permite la creación de la implementación "anillos", donde los administradores pueden especificar qué dispositivos instalación actualizaciones de calidad en primer lugar y que los instalará más adelante. Esto permite la confiabilidad y el rendimiento de las pruebas en un subconjunto de sistemas antes de implementar actualizaciones en toda la implementación completa sin la sobrecarga de administrar las actualizaciones de Windows en SCCM por ejemplo.
- WSUS y las actualizaciones de Windows para la empresa pueden ser [configurada al mismo tiempo](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) si así lo desea administración de ancho de banda y el control de las actualizaciones de Windows para la empresa proporciona.
- Actualizaciones de la característica. Consulte las notas adicionales que aparece a continuación.

## <a name="wsussccmhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[WSUS O SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Muy similar a Windows Update para la empresa, pero con la opción adicional de identificación específica KB dentro de cada "anillo" o toda la implementación. Cada actualización puede ser individualmente implementado y probado según se desee, en lugar de confiar en sólo un retraso. 
- Actualizaciones de la característica. Consulte las notas adicionales que aparece a continuación.


### <a name="feature-updates"></a>Actualizaciones de característica

A diferencia de calidad y no Deferable actualizaciones, Windows 10 "Característica Actualizaciones" (versiones principales del sistema operativo) sólo se instalarán después de que Microsoft prueba y valida una funcionalidad determinada actualizaciones con Microsoft los equipos locales. Incluso si se publicadas hasta el punto y anuales del canal (o destino si tiene sistemas establecida en dicho canal para las pruebas) o incluso manualmente inserta por su propio intentos o las configuraciones, no le permitirá la instalación hasta que se quite el bloqueo en nuestro final.

Salón de los equipos de Microsoft "de fábrica", con las manos desactiva el enfoque, no va a instalar una actualización de Windows o un dispositivo se reinicie automáticamente debido a una actualización de Windows. Sin embargo, los sistemas pueden descargar una actualización y esperar el siguiente reinicio que lo instale. A menos que alguien reinicia manualmente, instalación debe producirse durante el reinicio automático por la noche. Actualizaciones de Windows debe ser transparentes en la sala, la interfaz de usuario nunca debe ser interrumpido por actualizaciones de Windows.

Si opta por unirse a un dominio, use SCCM o WSUS y preste especial atención a las directivas o acciones que pueden ocasionar que el dispositivo de instalar una actualización o forzar un reinicio durante la jornada laboral. Si tiene sistemas en la implementación de reinicio durante el uso o alertas acerca de las actualizaciones de Windows a través de la interfaz de usuario, desea buscar en la configuración.