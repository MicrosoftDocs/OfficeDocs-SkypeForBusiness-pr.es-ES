---
title: Información general de administración para salas de Microsoft Teams
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Información general de administración para salas de Microsoft Teams.
ms.openlocfilehash: a55741fced90a62316ab8d046a91ee0364b314fd
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573566"
---
# <a name="management-overview"></a>Introducción a la administración

Es esencial que desarrolle y ejecute el mantenimiento y las operaciones constantes para asegurarse de que los sistemas de salas de Microsoft Teams estén disponibles para sus usuarios y ofrezcan una excelente experiencia de usuario. 

## <a name="monitoring"></a>Supervisión 

La supervisión de los sistemas de salas de Microsoft Teams consta de dos actividades clave:

- Supervisión de dispositivos, aplicaciones y dispositivos periféricos
- Supervisión de la calidad y la confiabilidad (CQD)

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a>Salas de supervisión de dispositivos, aplicaciones y dispositivos periféricos de Microsoft Teams

Para asegurarse de que los usuarios pueden usar las unidades de salas de Microsoft Teams, las unidades deben estar conectadas a la red con la aplicación salas de Microsoft Teams configurada correctamente y estar conectadas a dispositivos periféricos en funcionamiento. 

La información sobre el estado de la aplicación salas de Microsoft Teams y los dispositivos periféricos conectados está escrita por la aplicación salas de Microsoft Teams en el registro de eventos de Windows y documentada en [comprender las entradas del registro](azure-monitor-manage.md#understand-the-log-entries). 

|**Al**|**Posible**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (DWORD) 1  <br/> |Permite arrancar las salas de Microsoft Teams  <br/> |
|Administración de energía\> : on AC, apagar la pantalla después de 10 minutos  <br/> Administración de energía\> : on AC, no poner el sistema en suspensión  <br/> |Permite que las salas de Microsoft Teams desactiven las pantallas adjuntas y se reactiven automáticamente.  <br/> |
|net accounts /maxpwage:unlimited  <br/> O medios alternativos para deshabilitar la opción de caducidad de la contraseña en la cuenta local. Si esto no se realiza, la cuenta de Skype no podrá iniciar sesión indicando que la contraseña ha caducado. Tenga en cuenta que esto afectará todas las cuentas locales de la máquina y, por consiguiente, si no se configura esto, la cuenta administrativa del cuadro eventualmente también caducará.  <br/> |Permite que la cuenta de Skype siempre inicie sesión  <br/> |

La transferencia de archivos mediante directivas de grupo se trata en [configurar un elemento de archivo](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).
  
## <a name="remote-management-using-powershell"></a>Administración remota con PowerShell
<a name="RemotePS"> </a>

Le recomendamos que use Microsoft Operations Manager suite para supervisar los sistemas de salas de Microsoft Teams. Para obtener instrucciones sobre cómo configurar la supervisión y las alertas básicas, consulte [implementar la administración de salas de Microsoft Teams con Azure monitor](azure-monitor-deploy.md). 

Con esta guía, puede crear un panel fácil de usar para identificar cualquier problema con las unidades de salas de Microsoft Teams en toda su implementación. 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Confirme que va a usar Operations Management Suite para supervisar la implementación de las salas de Microsoft Teams.</li><li>Decida la lista de distribución de destino que usará para las alertas de correo electrónico.</li></ul>|
|![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Definir el método de supervisión de la calidad y la fiabilidad.</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>Supervisión de la calidad y la confiabilidad (CQD)

Le recomendamos que implemente procedimientos continuos de supervisión de la calidad operativa y la confiabilidad como parte de su implementación para controlar las tendencias de la calidad y la confiabilidad de las llamadas y las reuniones, identificar las áreas de preocupación y trabajar en la resolución. 

Al cargar la información de su edificio en el CQD, puede investigar tendencias de la calidad de las llamadas y de la fiabilidad en un nivel por construcción, lo que facilita la comparación de los edificios y concentra su atención en problemas específicos.

Le recomendamos que revise y siga la [Guía de revisión de la calidad de la experiencia](https://aka.ms/qerguide) para identificar tendencias de calidad y confiabilidad, y crear un plan de acción para resolverlos. 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a>Actualización de la aplicación Microsoft Teams Rooms OS and Microsoft Teams Rooms

Le recomendamos que actualice la aplicación Microsoft Teams Rooms OS and Microsoft Teams Rooms para beneficiarse de las actualizaciones y mejoras de productos. Para obtener instrucciones detalladas, consulte [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#software-updates). 

## <a name="windows-updates"></a>Actualizaciones de Windows

Salas de Microsoft Teams se ejecuta en Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) y recibe las mismas actualizaciones de Windows y OS que un escritorio estándar. Para obtener más información, consulte [administrar actualizaciones de Windows](updates.md) .


## <a name="troubleshooting"></a>Solución de problemas

Le recomendamos que configure las alertas de Operations Management Suite como se describe en la sección anterior, de modo que el equipo de operaciones y el Departamento de soporte técnico recibirán una alerta de problemas con cualquier problema de las salas de Microsoft Teams. Las opciones que tiene para la administración remota de PowerShell se describen en [administración remota con PowerShell](room-systems-v2-operations.md#remote-management-using-powershell). En el caso de que se desconecte un dispositivo periférico, es posible que deba depender de las "manos inteligentes" locales o de la asistencia de TI para investigar y volver a conectar los dispositivos. 

Para obtener más información sobre la solución de problemas y el modo de administración, consulte [administrar salas de Microsoft Teams](room-systems-v2-operations.md#admin-mode-and-device-management). 


## <a name="see-also"></a>Vea también

[Ayuda de Salas de Microsoft Teams](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Plan para salas de Microsoft Teams](skype-room-systems-v2-0.md)

[Implementar salas de Microsoft Teams](room-systems-v2.md)

[Configurar una consola de salas de Microsoft Teams](console.md)

[Administrar de forma remota la configuración de la consola de salas de Microsoft Teams con un archivo de configuración XML](xml-config-file.md)
