---
title: Compatibilidad con versiones
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: En este artículo se describe la compatibilidad del ciclo de vida de las salas de Microsoft Teams.
ms.openlocfilehash: 18d666e9fd0fa98e6c5a92ad7910cfe2adcb4a9e
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494725"
---
# <a name="microsoft-teams-room-app-version-support"></a>Compatibilidad de versión de la aplicación Microsoft Teams Room
 
Microsoft planea publicar las actualizaciones de salas de Microsoft Teams varias veces por año con cada actualización admitida durante doce (12) meses, a partir de la fecha de publicación de disponibilidad general (GA). Se proporcionará soporte técnico para todos los doce (12) meses. Sin embargo, nuestra estructura de soporte ahora es dinámica y evoluciona en dos fases de mantenimiento distintas que dependen de la disponibilidad de la última versión.

**Fase de mantenimiento de actualizaciones críticas y mantenimiento** \- Al ejecutar la versión más reciente de las salas de Microsoft Teams, recibirá actualizaciones periódicas, que contienen actualizaciones de seguridad y mantenimiento de servicios.

**Actualización de seguridad (solo) fase de mantenimiento** \- Después de que se publique una nueva versión, la compatibilidad con las ramas anteriores se reducirá a las actualizaciones de seguridad solo para el resto del ciclo de vida del soporte técnico actualizaciones de doce (12) meses.

> [!NOTE]
> La versión más reciente siempre está en la fase de mantenimiento de mantenimiento y actualizaciones críticas. Esto significa que, en el caso de que encuentre un defecto de código que garantice una actualización crítica, debe tener instalada la versión más reciente para poder recibir una corrección. Todas las demás versiones admitidas solo podrán recibir actualizaciones de seguridad.

Toda la asistencia finaliza después del ciclo de vida de doce (12) meses para una versión vencida o si se han publicado más de dos actualizaciones desde entonces. En ese momento, los clientes deben actualizar a una versión compatible.

Todas las versiones se enumeran en las notas de la [versión de Microsoft Teams Rooms](srs2-release-note.md).

# <a name="os-version-support"></a>Compatibilidad con la versión del sistema operativo
Las actualizaciones de características de Windows 10 para dispositivos que ejecutan salas de Microsoft Teams no se ofrecen durante 6 meses desde el momento en que Windows realiza una actualización de versión. Esto se logra colocando un bloque especial para los dispositivos de salas de Microsoft Teams en el canal de Windows Update para empresas (es decir, canal semianual) y a través de la configuración de la aplicación. Durante este período bloqueado, Microsoft realiza diversas pruebas en la vivienda y a través de nuestros socios OEM de dispositivos para asegurarse de que la nueva versión de Windows 10 funcione en consonancia con la aplicación de salas de Microsoft Teams y los periféricos conectados a ella. Esto es importante para garantizar la seguridad del dispositivo, la experiencia coherente del usuario y garantizar la calidad de las experiencias que se ofrecen a través de la aplicación salones de Microsoft Teams.   

Desde el momento en que se eleva el bloque de tiempo (es decir, la actualización de características de Windows 10 se ofrece para su descarga en estos dispositivos), salas de Microsoft Teams es compatible con la versión específica de características de Windows 10 por período de 12 meses en línea con la Directiva de compatibilidad de aplicaciones. Como las actualizaciones de características de Windows 10 se ofrecen aproximadamente cada 6 meses, esto también significa que Microsoft Teams tendrá dos versiones adicionales para comprobar por el momento de finalizar la compatibilidad con la versión actual. Esto también significa que una versión de Windows 10 se desbloqueará cada 6 meses para todos los clientes de las salas de Microsoft Teams. A medida que vaya continuamente haciendo cambios en las aplicaciones y se desarrollen con la última versión de Windows desbloqueada, en algunos casos necesitará depender de las características de Windows disponibles en las versiones más recientes de Windows y el hecho de que sea más difícil que Microsoft realice cambios en la versión de 12-18 meses de edad. Para asegurarse de que obtiene la corrección de la aplicación para un problema que se encuentra en su dispositivo de salas de Microsoft Teams, recomendamos a todos los clientes que actualicen estos dispositivos a la última actualización de características de Windows 10 que se ofrece para mantenerse dentro de la guía de la versión de Windows.

Como tal, los dispositivos de salas de Microsoft Teams requieren Windows 10 versión 1709 como la versión mínima admitida a partir del 2019 de mayo. No se ofrecerán nuevas versiones de la aplicación a los sistemas de las versiones 1703 o anteriores de Windows 10.

> [!NOTE]
> Cuando un dispositivo de salas de Microsoft Teams es compatible con la siguiente versión del sistema operativo Windows 10, el dispositivo se actualiza automáticamente a la siguiente versión a través de Windows Update. Los dispositivos de las salas de Microsoft Teams no se deben actualizar manualmente a la siguiente versión de Windows 10 o mediante la habilitación de directivas de grupo de Windows Update para empresas mediante "Seleccione el nivel de preparación de Windows para las actualizaciones que desea recibir" y "seleccione Cuándo Se reciben las opciones vista previa y actualizaciones de características a través de un GPO. La habilitación de estas directivas de grupo puede provocar problemas entre la actualización del sistema operativo Windows 10 y la aplicación salas de Microsoft Teams. 
 
<a name="See"> </a>  
## <a name="see-also"></a>Vea también

[Ayuda de Salas de Microsoft Teams](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Notas de la versión de Microsoft Teams Rooms](srs2-release-note.md)

[Plan para salas de Microsoft Teams](skype-room-systems-v2-0.md)
