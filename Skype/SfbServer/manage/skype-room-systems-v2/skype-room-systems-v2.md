---
title: Introducción a la administración de salas de equipos de Microsoft
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: Introducción a la administración de salas de equipos de Microsoft.
ms.openlocfilehash: a06ffc6bb0aa69b493c95a516946c322034913f8
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012496"
---
# <a name="management-overview"></a>Introducción a la administración 

Es esencial que desarrollar y ejecutar el mantenimiento continuado y operaciones para asegurarse de que los sistemas de salas de equipos de Microsoft están disponibles para los usuarios y ofrecen a un usuario excelente experimentan. 

## <a name="monitoring"></a>Supervisión 

Supervisión de sistemas de salas de equipos de Microsoft consta de dos actividades clave:

-  Dispositivo, la aplicación y la supervisión de dispositivos periféricos

-  Calidad y confiabilidad de supervisión (CQD)

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a>Dispositivo de salas de equipos de Microsoft, la aplicación y la supervisión de dispositivos periféricos

Para asegurarse de que los usuarios podrán utilizar las unidades locales de los equipos de Microsoft, las unidades deben estar en, conectado a la red con la aplicación de salas de equipos de Microsoft configurada correctamente y estar conectadas a dispositivos periféricos funcionamiento. 


Información sobre el estado de la aplicación de Microsoft salones de los equipos y dispositivos periféricos conectados es escrita por la aplicación de salas de equipos de Microsoft para el registro de eventos de Windows y que se documentaron en [comprender las entradas del registro](azure-monitor.md#understand-the-log-entries). 

|**Configuración**|**Permite**|
|:-----|:-----|
|HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1  <br/> |Permite salones de los equipos de Microsoft para que se inicie  <br/> |
|Administración de energía -\> en AC, desactivar pantalla después de 10 minutos  <br/> Administración de energía -\> en AC, nunca colocar del sistema al modo de suspensión  <br/> |Permite salones de los equipos de Microsoft desactivar muestra adjunto y reactivar automáticamente  <br/> |
|net accounts /maxpwage:unlimited  <br/> O medios alternativos para deshabilitar la opción de caducidad de la contraseña en la cuenta local. Si esto no se realiza, la cuenta de Skype no podrá iniciar sesión indicando que la contraseña ha caducado. Tenga en cuenta que esto afectará todas las cuentas locales de la máquina y, por consiguiente, si no se configura esto, la cuenta administrativa del cuadro eventualmente también caducará.  <br/> |Permite que la cuenta de Skype siempre inicie sesión  <br/> |
   
Transferencia de archivos mediante directivas de grupo se describe en [configurar un elemento de archivo](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).
  
## <a name="remote-management-using-powershell"></a>Administración remota con PowerShell
<a name="RemotePS"> </a>

Se recomienda que utilice el conjunto de aplicaciones de Microsoft Operations Manager para supervisar los sistemas de salas de equipos de Microsoft. Para obtener instrucciones acerca de cómo configurar la supervisión y alertas básicas, vea [administración de implementación de salas de equipos de Microsoft con el Monitor de Azure](../../deploy/deploy-clients/azure-monitor.md). 

Uso de esta guía, puede crear un panel simple de usar para identificar los problemas con las unidades locales de los equipos de Microsoft a través de la implementación. 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Confirme que usará el conjunto de aplicaciones de las operaciones de administración para supervisar la implementación de salas de equipos de Microsoft.</li><li>Decidir que va a utilizar para alertas de correo electrónico de la lista de distribución de destino.</li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Definir la calidad y el enfoque de supervisión de la confiabilidad.</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>Calidad y confiabilidad de supervisión (CQD)

Se recomienda que implemente calidad operativa continuada y confiabilidad procedimientos de supervisión como parte de su implementación para supervisar las tendencias de llamada y la calidad de la reunión y la confiabilidad, que identifica las áreas de preocupación y trabajar hacia una resolución. 

Cuando se carga la información de creación en CQD puede investigar las tendencias de calidad y la confiabilidad de llamadas en un nivel por edificio, lo que facilita la comparación de los edificios y centra la atención en problemas específicos. Para obtener más información, descargue el [Monitor-CQD de Skype para entrega en línea de negocio y la Guía de operaciones](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15). 

Se recomienda que revise y siga la [Guía de revisión de calidad de experiencia](https://aka.ms/qerguide) para identificar las tendencias de calidad y la confiabilidad y crear un plan de acción para resolverlos conflictos. 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a>Actualización de la aplicación de sistema operativo de salones de los equipos de Microsoft y salas de equipos de Microsoft

Se recomienda que actualizar la aplicación de sistema operativo de salones de los equipos de Microsoft y salas de equipos de Microsoft para sacar partido de las actualizaciones del producto y las mejoras. Para obtener instrucciones detalladas, consulte [Manage Rooms de los equipos de Microsoft](room-systems-v2-operations.md#software-updates). 

## <a name="windows-updates"></a>Actualizaciones de Windows

Salones de los equipos de Microsoft se ejecuta en Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) y recibe las compilaciones de actualizaciones de Windows y el sistema operativo mismas como un escritorio estándar. Para obtener información detallada, vea [Administrar actualizaciones de Windows](updates.md) .


## <a name="troubleshooting"></a>Solución de problemas

Se recomienda que configure alertas del conjunto de aplicaciones de administración de operaciones tal como se describe en la sección anterior para que su equipo de operaciones y el departamento de soporte técnico le avisará de que cualquier problema de salas de equipos de Microsoft. Se describen las opciones disponibles para la administración remota de PowerShell en [PowerShell de uso de administración remota](room-systems-v2-operations.md#remote-management-using-powershell). En caso de que se desconecta un dispositivo periférico, es posible que necesite se basan en locales "inteligentes manos" o soporte de TI para investigar y volver a conectar los dispositivos. 

Para obtener más información sobre el modo de administración y solución de problemas, vea [Administrar salones de los equipos de Microsoft](room-systems-v2-operations.md#admin-mode-and-device-management). 


## <a name="see-also"></a>Consulte también

[Ayuda de salas de equipos de Microsoft](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Plan para salas de equipos de Microsoft](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[Implementación de salas de equipos de Microsoft](../../deploy/deploy-clients/room-systems-v2.md)

[Configurar una consola de salas de equipos de Microsoft](../../deploy/deploy-clients/console.md)

[Administrar una configuración de la consola Microsoft salones de los equipos de forma remota con un archivo de configuración XML](xml-config-file.md)
