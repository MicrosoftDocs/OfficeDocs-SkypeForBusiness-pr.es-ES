---
title: Habilitar la grabación de detalles de llamadas en Skype Empresarial Server
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
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Summary: Learn how to enable Call detail recording (CDR) records in Skype Empresarial Server.'
ms.openlocfilehash: 1d09e637d75b9617abf669f75e96076333380a075010bd3d641f4c5189be9d89
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301386"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>Habilitar la grabación de detalles de llamadas en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo habilitar registros de registro detallado de llamadas (CDR) en Skype Empresarial Server.

El registro detallado de llamadas (CDR) registra la información de uso y diagnóstico sobre actividades punto a punto, incluida la mensajería instantánea, llamadas de voz sobre IP (VoIP), uso compartido de aplicaciones, transferencia de archivos y reuniones. Los datos de uso pueden servir para calcular el retorno de la inversión y los datos de diagnóstico se pueden usar para solucionar problemas de actividades punto a punto y reuniones.

Use el procedimiento siguiente para habilitar el registro detallado de llamadas (CDR) en toda la organización o en cada sitio de la organización.

> [!NOTE]
> Para poder habilitar el CDR debe configurar la supervisión y una base de datos de supervisión. Para obtener más información, consulte [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>Para habilitar CDR con Skype Empresarial Server panel de control

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control.

3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, en **Registro detallado de llamadas**.

4. En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la lista, seleccione **Acción** y, a continuación, haga clic en **Habilitar CDR**.

    > [!NOTE]
    > CDR habilitado de forma predeterminada.

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Habilitar CDR mediante el uso Windows PowerShell cmdlets

Puede habilitar cdr mediante Windows PowerShell y el cmdlet **Set-CsCdrConfiguration.** Puede ejecutar este cmdlet desde el Shell de administración Skype Empresarial Server desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell para conectarse a Skype Empresarial Server, vea el artículo de blog "Inicio rápido: Administración de [Microsoft Lync Server 2010 mediante PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876) El proceso es el mismo en Skype Empresarial Server.

### <a name="to-enable-cdr-for-a-single-location"></a>Para habilitar CDR para una única ubicación

 Para deshabilitar CDR, establezca el parámetro EnableCDR en True ($True).

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>Para deshabilitar CDR para una única ubicación

 Para deshabilitar CDR, establezca el parámetro EnableCDR en False ($False). Deshabilitar CDR no desinstala la supervisión. Pausa la recopilación y el almacenamiento de datos CDR.

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>Utilizar un único comando para habilitar CDR en varias ubicaciones

 Este comando habilita CDR para todos los parámetros de CDR que se encuentran actualmente en uso en su organización.

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

Para obtener más información, vea el tema de ayuda del cmdlet [Set-CsCdrConfiguration.](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)

## <a name="see-also"></a>Consulte también

[Planeación de la supervisión](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[Implementación de supervisión](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)