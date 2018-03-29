---
title: Habilitar calidad de la experiencia en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Resumen: Conozca cómo habilitar calidad de experiencia (QoE) en Skype para Business Server 2015.'
ms.openlocfilehash: 8c63a1bf493e601c4936b83cc9edfaa6e3727f26
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="enable-quality-of-experience-in-skype-for-business-server-2015"></a>Habilitar calidad de la experiencia en Skype Empresarial Server 2015
 
**Resumen:** obtener información sobre cómo habilitar la calidad de la experiencia (QoE) en Skype para Business Server 2015.
  
La calidad de la experiencia (QoE) registra datos numéricos que indican la calidad de los medios e información sobre los participantes, nombres de los dispositivos, controladores, direcciones IP y tipos de extremos que se usan en las llamadas y las sesiones. Para obtener más información, vea [Planear la supervisión](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) en la documentación de planeamiento.
  
Para habilitar QoE en toda la organización o en cada uno de sus sitios, realice el procedimiento siguiente.
  
> [!NOTE]
> Para habilitar QoE, en primer lugar necesita instalar el Servidor de supervisión y conectarlo a una base de datos back-end de supervisión. Para obtener información detallada, vea [Implementación de supervisión](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx). 
  
### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>Para habilitar QoE mediante Skype para Panel de Control de servidor empresarial

1.  Desde una cuenta de usuario que es miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en el que implementa Skype para Business Server 2015.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, luego, en **Datos sobre la calidad de la experiencia**. 
    
4. En la página **Datos de calidad de la experiencia**, haga clic en la colección adecuada de la tabla, en **Acción** y en **Habilitar QoE**.
    
## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Habilitar QoE mediante Cmdlets de Windows PowerShell

Puede habilitar QoE mediante Windows PowerShell y el cmdlet **Set-CsQoEConfiguration** . Este cmdlet se puede ejecutar desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-enable-qoe-for-a-single-location"></a>Para habilitar QoE para una sola ubicación:

 Para habilitar QoE, defina el parámetro EnableQoE en True ($True).
    
  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>Para deshabilitar QoE para una ubicación única:

 Para deshabilitar QoE, establezca el parámetro EnableQoE en False ($False). Así no se desinstala la supervisión. Se detiene la recopilación y el almacenaje de los datos de QoE.
    
  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>Para habilitar QoE en varias ubicaciones con un comando único:

 Este comando habilita QoE para todos los valores de configuración de QoE que se usan actualmente en la organización.
    
  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

Para obtener más información, consulte [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).
  
## <a name="see-also"></a>Vea también

[Planeamiento para la supervisión](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)
  
[Implementación de la supervisión](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

