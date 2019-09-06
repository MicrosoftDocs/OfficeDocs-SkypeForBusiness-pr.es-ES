---
title: Administrar actualizaciones de Windows para salas de Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Administrar actualizaciones de Windows para salas de Microsoft Teams
ms.openlocfilehash: 09be03b0308dfcf00a39421e2e84b75fe94a9fae
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775321"
---
# <a name="manage-windows-updates"></a>Administrar actualizaciones de Windows

Salas de Microsoft Teams se ejecuta en Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) y recibe las mismas actualizaciones de Windows y OS que un escritorio estándar.

Las actualizaciones de Windows se pueden administrar de varias maneras diferentes:

## <a name="hands-off-approach"></a>Enfoque de manos libres 
- Las actualizaciones se pueden descargar directamente desde actualizaciones de Windows e instalarse de forma automática fuera de horas. Si no se realiza ningún cambio en la configuración, este es el estado predeterminado.
- Las actualizaciones no aplazables instalarán el día, una de las versiones automáticamente. 
- Las actualizaciones y drivers de calidad descargarán e instalarán el día uno automáticamente. 
- Actualizaciones de características. Consulte las notas adicionales a continuación. 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a>[Actualizaciones de Windows para empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO o Intune)   
- Las actualizaciones se descargan desde WU o WSUS, pero con retrasos configurados más allá de la fecha de lanzamiento original de KB. 
- Combinado con varias unidades organizativas o directivas filtradas, permite la creación de "timbres" de implementación, donde los administradores pueden especificar qué dispositivos instalan primero las actualizaciones de calidad y cuáles se instalarán más adelante. Esto permite pruebas de confiabilidad y rendimiento en un subconjunto de sistemas antes de implementar las actualizaciones en toda la implementación sin la sobrecarga de administrar las actualizaciones de Windows en SCCM, por ejemplo.
- Las actualizaciones de WSUS y Windows para empresas pueden [configurarse al mismo tiempo](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) si quiere tanto la administración del ancho de banda como el control que ofrece Windows Updates para empresas.
- Actualizaciones de características. Consulte las notas adicionales a continuación.

## <a name="wsussccmhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- De manera muy similar a Windows Update para empresas, pero con la opción adicional de segmentar las KB específicas dentro de cada "timbre" o toda la implementación. Cada actualización se puede implementar y probar individualmente en la misma, en lugar de confiar únicamente en un retraso. 
- Actualizaciones de características. Consulte las notas adicionales a continuación.


### <a name="feature-updates"></a>Actualizaciones de características

A diferencia de la calidad y las actualizaciones no aplazables, las actualizaciones de características de Windows 10 (versiones principales del sistema operativo) solo se instalarán después de que Microsoft pruebe y valide una funcionalidad de actualizaciones determinada con salas de Microsoft Teams. Aunque se publique para el canal semianual (o se destinan a los sistemas establecidos en ese canal para realizar pruebas) o incluso a la inserción manual por sus propios intentos o configuraciones, no se permitirá la instalación hasta que se elimine el bloqueo de nuestro extremo.

La sala de Microsoft Teams "de uso no actualizado", con el método de manos libres, no instalará Windows Update ni reiniciará automáticamente un dispositivo debido a una actualización de Windows. Sin embargo, los sistemas pueden descargar una actualización y esperar a que se reinicie la próxima vez. A menos que alguien lo reinicie manualmente, la instalación debe realizarse durante el reinicio automático nocturno. Las actualizaciones de Windows deberían ser transparentes en el salón, mientras que las actualizaciones de Windows nunca las interrumpan.

Si elige unirse a un dominio, use SCCM o WSUS y preste especial atención a las directivas o acciones que pueden provocar que el dispositivo Instale una actualización o que se reinicie durante el horario comercial. Si tiene sistemas en la implementación que se está reiniciando durante el uso o la alerta sobre actualizaciones de Windows a través de la interfaz de usuario, le interesará examinar la configuración.
