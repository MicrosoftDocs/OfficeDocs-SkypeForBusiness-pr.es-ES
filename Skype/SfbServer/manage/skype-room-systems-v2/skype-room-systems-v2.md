---
title: Introducción a la administración de sistemas de salón de Skype v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
description: Introducción a la administración de sistemas de salón de Skype v2.
ms.openlocfilehash: 81ad0e43f68127e3a178434ebdd8ac8a43c94adc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21014906"
---
# <a name="management-overview"></a>Introducción a la administración 

Es esencial que desarrollar y ejecutar el mantenimiento continuado y operaciones para asegurarse de que los sistemas de v2 de Skype salón sistemas están disponibles para los usuarios y ofrecen a un usuario excelente experimentan. 

## <a name="monitoring"></a>Supervisión 

Sistemas de salón de Skype v2 sistemas de supervisión consta de dos actividades clave:

-  Dispositivo, la aplicación y la supervisión de dispositivos periféricos

-  Calidad y confiabilidad de supervisión (CQD)

### <a name="skype-room-systems-v2-device-application-and-peripheral-device-monitoring"></a>Dispositivo v2 de Skype salón sistemas, aplicaciones y supervisión de dispositivos periféricos

Para asegurarse de que los usuarios podrán utilizar las unidades de sistemas de salón de Skype v2, las unidades deben estar en, conectado a la red con la aplicación de v2 de sistemas de salón de Skype configurada correctamente y estar conectadas a dispositivos periféricos funcionamiento. 


Información sobre el estado de la aplicación de v2 de Skype salón sistemas y dispositivos periféricos conectados está escrita por la aplicación de v2 de sistemas de salón de Skype para el registro de eventos de Windows y documenta [en este artículo](oms.md#understand-the-log-entries). 

|**Configuración**|**Permite**|
|:-----|:-----|
|HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1  <br/> |Permite v2 de sistemas de salón de Skype iniciar copia de seguridad  <br/> |
|Administración de energía -\> en AC, desactivar pantalla después de 10 minutos  <br/> Administración de energía -\> en AC, nunca colocar del sistema al modo de suspensión  <br/> |Permite v2 de sistemas de salón de Skype para desactivar muestra adjunto y reactivar automáticamente  <br/> |
|net accounts /maxpwage:unlimited  <br/> O medios alternativos para deshabilitar la opción de caducidad de la contraseña en la cuenta local. Si esto no se realiza, la cuenta de Skype no podrá iniciar sesión indicando que la contraseña ha caducado. Tenga en cuenta que esto afectará todas las cuentas locales de la máquina y, por consiguiente, si no se configura esto, la cuenta administrativa del cuadro eventualmente también caducará.   <br/> |Permite que la cuenta de Skype siempre inicie sesión  <br/> |
   
Transferencia de archivos mediante directivas de grupo se describe en [configurar un elemento de archivo](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).
  
## <a name="remote-management-using-powershell"></a>Administración remota con PowerShell
<a name="RemotePS"> </a>


Se recomienda que utilice el conjunto de aplicaciones de Microsoft Operations Manager para supervisar los sistemas de v2 de sistemas de salón de Skype. Para obtener instrucciones acerca de cómo configurar la supervisión y alertas básicas, vea [administración de v2 de implementar sistemas de salón de Skype con OMS](../../deploy/deploy-clients/with-oms.md). 

Uso de esta guía, puede crear un panel simple de usar para identificar los problemas con las unidades de v2 de sistemas de salón de Skype en toda la implementación. 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Confirme que usará el conjunto de aplicaciones de las operaciones de administración para supervisar la implementación de sistemas de salón de Skype v2.</li><li>Decidir que va a utilizar para alertas de correo electrónico de la lista de distribución de destino.</li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Definir la calidad y el enfoque de supervisión de la confiabilidad.</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>Calidad y confiabilidad de supervisión (CQD)

Se recomienda que implemente calidad operativa continuada y confiabilidad procedimientos de supervisión como parte de su implementación para supervisar las tendencias de llamada y la calidad de la reunión y la confiabilidad, que identifica las áreas de preocupación y trabajar hacia una resolución. 

Cuando se carga la información de creación en CQD puede investigar las tendencias de calidad y la confiabilidad de llamadas en un nivel por edificio, lo que facilita la comparación de los edificios y centra la atención en problemas específicos. Para obtener más información, descargue el [Monitor-CQD de Skype para entrega en línea de negocio y la Guía de operaciones](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15). 

Se recomienda que revise y siga la [Guía de revisión de calidad de experiencia](https://aka.ms/qerguide) para identificar las tendencias de calidad y la confiabilidad y crear un plan de acción para resolverlos conflictos. 

## <a name="updating-the-skype-room-systems-v2-os-and-skype-room-systems-application"></a>Actualización de la aplicación de sistema operativo y sistemas de salón de Skype de v2 sistemas de salón de Skype 

Se recomienda que actualizar para sacar partido de las actualizaciones del producto y mejoras en la aplicación v2 de sistemas de salón de Skype v2 OS y sistemas de salón de Skype. Para obtener instrucciones detalladas, consulte [v2 de administración de sistemas de salón de Skype](room-systems-v2-operations.md#software-updates). 

## <a name="troubleshooting"></a>Solución de problemas

Se recomienda que configure alertas del conjunto de aplicaciones de administración de operaciones tal como se describe en la sección anterior para que su equipo de operaciones y el departamento de soporte técnico le avisará de que cualquier problema de v2 de sistemas de salón de Skype. Se describen las opciones disponibles para la administración remota de PowerShell en [PowerShell de uso de administración remota](room-systems-v2-operations.md#remote-management-using-powershell). En caso de que se desconecta un dispositivo periférico, es posible que necesite se basan en locales "inteligentes manos" o soporte de TI para investigar y volver a conectar los dispositivos. 

Para obtener más información sobre el modo de administración y solución de problemas, vea [administrar sistemas de salón de Skype v2](room-systems-v2-operations.md#admin-mode-and-device-management). 

## <a name="see-also"></a>Vea también

[Ayuda de la versión 2 de sistemas de salón de Skype](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Plan para Sistemas de salas de Skype v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[Implementar Sistemas de salas de Skype v2](../../deploy/deploy-clients/room-systems-v2.md)

[Configurar una consola de Sistemas de salas de Skype v2](../../deploy/deploy-clients/console.md)

[Administrar la configuración de una consola de Sistemas de salas de Skype v2 de forma remota con un archivo XML de configuración](xml-config-file.md)
