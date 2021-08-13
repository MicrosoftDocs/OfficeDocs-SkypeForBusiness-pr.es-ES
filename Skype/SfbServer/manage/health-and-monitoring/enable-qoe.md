---
title: Habilitar la calidad de la experiencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Summary: learn how to enable Quality of Experience (QoE) in Skype Empresarial Server.'
ms.openlocfilehash: 12428d02784c858f07f8aeb937420299f0c5e1220772e19c49c388a49eef216a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301366"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>Habilitar la calidad de la experiencia en Skype Empresarial Server

**Summary:** learn how to enable Quality of Experience (QoE) in Skype Empresarial Server.

La calidad de la experiencia (QoE) registra datos numéricos que indican la calidad de los medios e información sobre los participantes, nombres de los dispositivos, controladores, direcciones IP y tipos de extremos que se usan en las llamadas y las sesiones. Para más información, consulte [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) en la documentación de planeación.

Para habilitar QoE en toda la organización o en cada uno de sus sitios, realice el procedimiento siguiente.

> [!NOTE]
> Para habilitar QoE, en primer lugar debe instalar el Servidor de supervisión y conectarlo a una base de datos back-end de supervisión. Para más información, consulte [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>Para habilitar QoE mediante el panel Skype Empresarial Server control

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control.

3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y en **Datos de calidad de la experiencia**.

4. En la página **Datos de calidad de la experiencia**, haga clic en la colección adecuada de la tabla, en **Acción** y en **Habilitar QoE**.

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Habilitar QoE mediante cmdlets Windows PowerShell de seguridad

Puede habilitar QoE mediante Windows PowerShell y el cmdlet **Set-CsQoEConfiguration.** Puede ejecutar este cmdlet desde el Shell de administración Skype Empresarial Server desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell para conectarse a Skype Empresarial Server, vea el artículo de blog "Inicio rápido: Administración de [Microsoft Lync Server 2010 mediante PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876) El proceso es el mismo en Skype Empresarial Server.

### <a name="to-enable-qoe-for-a-single-location"></a>Para habilitar QoE para una sola ubicación:

 Para habilitar QoE, defina el parámetro EnableQoE en True ($True).

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>Para deshabilitar QoE para una ubicación única:

 Para deshabilitar QoE, establezca el parámetro EnableQoE en False ($False). Así no se desinstala la supervisión. Se detiene la recopilación y el almacenaje de los datos de QoE.

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>Para habilitar QoE en varias ubicaciones con un comando único:

 Este comando habilita QoE para todos los valores de configuración de QoE que se usan actualmente en la organización.

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

Para obtener más información, [vea Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).

## <a name="see-also"></a>Consulte también

[Planeación de la supervisión](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[Implementación de supervisión](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)