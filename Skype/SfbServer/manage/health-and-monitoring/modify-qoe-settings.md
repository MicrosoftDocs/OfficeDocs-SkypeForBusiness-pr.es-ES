---
title: Modificar la configuración de la calidad de la experiencia en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Resumen: Aprenda a especificar la retención de los datos de QoE en Skype empresarial Server.'
ms.openlocfilehash: 89e20b18aa285bd4ee61df12c822e487dd6b37a4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280008"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>Modificar la configuración de la calidad de la experiencia en Skype empresarial Server

**Resumen:** Aprenda a especificar la retención de los datos de QoE en Skype empresarial Server.

De forma predeterminada, los datos de calidad de la experiencia (QoE) se depuran una vez transcurridos 60 días. Puede usar la configuración de la página **Datos de calidad de la experiencia** para conservar los datos durante un periodo de tiempo mayor o menor. Si deshabilita QoE, los datos que se recopilaron antes de que se habilitara se someterán también a la depuración.

> [!NOTE]
> Configure el registro detallado de llamadas (CDR) y QoE para que conserven los datos durante el mismo número de días. Cada llamada en los informes de detalles de llamadas (CDR), que se encuentra disponible en la página principal de los informes del servidor de supervisión, incluye la información del CDR y de la QoE. Si la duración de la depuración para los CDR y la QoE es diferente, es posible que algunas llamadas solo incluyan datos de CDR, mientras que otras solo incluirán datos de la QoE.

El procedimiento siguiente describe cómo establecer la configuración de la depuración para los datos de la QoE.

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>Para especificar la retención de datos de QoE con el panel de control de Skype empresarial Server

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte **Delegate Setup Permissions**.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.

3. En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, luego, en **Datos sobre la calidad de la experiencia**.

4. En la página **Datos sobre la calidad de la experiencia**, haga clic en el sitio apropiado de la tabla, haga clic en **Editar** y, luego, en **Mostrar detalles**.

5. Para activar la depuración, seleccione **Habilitar depuración de QoE**.

6. En **Conservar QoE durante un máximo de (días)**, seleccione la cantidad máxima de días durante los que se necesitan conservar los datos de la QoE.

7. Haga clic en **Confirmar**.

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Especificación de la retención de QoE mediante cmdlets de Windows PowerShell

Puede crear la configuración de retención de QoE mediante Windows PowerShell y el cmdlet **set-CsQoEConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype empresarial Server.

### <a name="to-specify-qoe-retention-for-a-specific-location"></a>Para especificar la retención de la QoE de una ubicación específica

- Este comando permite habilitar la depuración de datos de la QoE en el sitio de Redmond, así como configurar el sitio de manera que mantenga los datos de la QoE durante 20 días.

  ```
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>Para especificar la retención de la QoE de varias ubicaciones

- Este comando permite configurar la retención de todas las opciones de configuración de QoE que se usan en una organización.

  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) .

## <a name="see-also"></a>Vea también

[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
