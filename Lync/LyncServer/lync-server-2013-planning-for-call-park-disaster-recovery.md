---
title: "Lync Server 2013: Planear recuperación ante desastres de estacionamiento de llamadas"
TOCTitle: Planear la recuperación ante desastres del estacionamiento de llamadas
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48277235
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planear la recuperación ante desastres del estacionamiento de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-30_

En esta sección se describen algunas formas de preparar la Aplicación de estacionamiento de llamadas para la recuperación ante desastres y algunas consideraciones sobre el proceso de recuperación ante desastres.

## Preparación para la recuperación ante desastres de Estacionamiento de llamadas

Recuerde las siguientes prácticas recomendadas a la hora de preparar y llevar a cabo procedimientos de recuperación ante desastres.

  - Planee la recuperación ante desastres cuando realice la planeación de capacidad. Para ver la capacidad de recuperación ante desastres, cada grupo de servidores de un grupo emparejado debe poder gestionar las cargas de trabajo de los servicios de Estacionamiento de llamadas en ambos grupos de servidores. Para obtener información acerca de la planeación de capacidad de Estacionamiento de llamadas, consulte [Planificar la capacidad para el estacionamiento de llamadas en Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).

  - Durante la recuperación ante desastres, los usuarios que hayan sido redirigidos al grupo de servidores de copia de seguridad como parte del proceso de conmutación por error usan el servicio Estacionamiento de llamadas implementado en el grupo de servidores de copia de seguridad. En consecuencia, la compatibilidad con Estacionamiento de llamadas durante la recuperación ante desastres requiere que Aplicación de estacionamiento de llamadas se implemente y habilite tanto en el grupo de servidores principal como en el de copia de seguridad.

  - Cada grupo de servidores debe tener un intervalo válido de números de órbita para que lo usen los usuarios hospedados en dicho grupo para estacionar llamadas.

  - Conserve siempre una copia de seguridad aparte de la música en espera personalizada que se haya cargado para Estacionamiento de llamadas. El proceso de recuperación ante desastres de Lync Server 2013 no realiza la copia de seguridad de estos archivos, por lo que se perderán si los archivos cargados en el grupo de servidores se dañan o borran.

## Consideraciones sobre la recuperación ante desastres de Estacionamiento de llamadas

Solo puede definir un conjunto de opciones de configuración de Aplicación de estacionamiento de llamadas y un archivo de audio de música en espera personalizada por cada grupo de servidores. Estas configuraciones incluyen el umbral de tiempo en espera, música en espera, número máximo de intentos de respuesta de llamadas y el URI del tiempo en espera. Para ver estas opciones de configuración, ejecute el cmdlet **Get-CsCpsConfiguration**. Encontrará información detallada sobre el cmdlet **Get-CsCpsConfiguration** en [Get-CsCpsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCpsConfiguration).

Durante la recuperación ante desastres, Estacionamiento de llamadas usa la Aplicación de estacionamiento de llamadas en el grupo de servidores de reserva, de modo que no hay una copia de seguridad de la configuración del grupo de servidores principal. Si no se puede recuperar el grupo de servidores principal y se implementa un nuevo grupo para sustituirlo, la configuración del grupo de servidores principal se perderá y tendrá que volver a configurar las opciones de Estacionamiento de llamadas y los archivos de audio de música en espera personalizados.

Si implementa un grupo de servidores nuevo con un nombre de dominio completo (FQDN) diferente para sustituir al principal, tendrá que volver a asignar todos los intervalos de órbita de Estacionamiento de llamadas asociados al grupo de servidores principal al FQDN del grupo nuevo. Para ello, puede usar el cmdlet Panel de control de Lync Server o el **Set-CsCallParkOrbit**. Si desea información sobre el cmdlet **Set-CsCallParkOrbit**, consulte [Set-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkOrbit).

