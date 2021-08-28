---
title: Modificar la configuración de calidad de la experiencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Summary: Learn how to specify retention of QoE data in Skype Empresarial Server.'
ms.openlocfilehash: 54cb02e17106d2eee61bca8c171f6b16985d0dbc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614090"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>Modificar la configuración de calidad de la experiencia en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo especificar la retención de datos de QoE en Skype Empresarial Server.

De forma predeterminada, los datos de calidad de la experiencia (QoE)se depuran una vez hayan transcurrido 60 días. Puede usar la configuración de la página **Datos de calidad de la experiencia** para conservar los datos durante un periodo de tiempo mayor o menor. Si deshabilita QoE, los datos que se recopilaron antes de que se habilitara se someterán también a la depuración.

> [!NOTE]
> Configure el registro de detalles de la llamada (CDR) y QoE para que conserven los datos durante el mismo número de días. Cada llamada en el registro de detalles de la llamada (CDR), que se encuentra disponible en la página principal de los informes del servidor de supervisión, incluye la información del CDR y de la QoE. Si la duración de la depuración para los CDR y la QoE es diferente, es posible que algunas llamadas solo incluyan datos de CDR, mientras que otras solo incluirán datos de la QoE.

El procedimiento siguiente describe cómo establecer la configuración de la depuración para los datos de la QoE.

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>Para especificar la retención de datos de QoE mediante Skype Empresarial Server Panel de control

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol CsVoiceAdministrator, CsServerAdministrator, o CsAdministrator. Para obtener información detallada, consulte **Delegación de permisos de instalación**.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control.

3. En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Datos sobre la calidad de la experiencia**.

4. En la página **Calidad de la experiencia**, haga clic en el sitio apropiado de la tabla, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.

5. Para activar la depuración, seleccione **Habilitar depuración de QoE**.

6. En **Conservar QoE durante un máximo de (días)** Seleccione el número máximo de días durante los que se deben conservar los datos de la QoE.

7. Haga clic en **Confirmar**.

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Especificación de la retención de QoE mediante Windows PowerShell cmdlets

Puede crear la configuración de retención de QoE mediante Windows PowerShell y el cmdlet **Set-CsQoEConfiguration.** Puede ejecutar este cmdlet desde el Shell de administración Skype Empresarial Server desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell para conectarse a Skype Empresarial Server, vea el artículo de blog "Inicio rápido: Administración de [Microsoft Lync Server 2010 mediante PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876) El proceso es el mismo en Skype Empresarial Server.

### <a name="to-specify-qoe-retention-for-a-specific-location"></a>Para especificar la retención de la QoE de una ubicación específica

- Este comando permite habilitar la depuración de datos de la QoE en el sitio de Redmond, así como configurar el sitio de manera que mantenga los datos de la QoE durante 20 días.

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>Para especificar la retención de la QoE de varias ubicaciones

- Este comando permite configurar la retención de todas las opciones de configuración de QoE que se usan en una organización.

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

Para obtener más información, vea el tema de ayuda del cmdlet [Set-CsQoEConfiguration.](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)

## <a name="see-also"></a>Consulte también

[Implementación de supervisión](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)