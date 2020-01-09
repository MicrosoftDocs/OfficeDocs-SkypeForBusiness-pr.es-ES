---
title: Habilitar la grabación de detalles de llamadas en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Resumen: Aprenda a habilitar registros de grabación de detalles de llamadas (CDR) en Skype empresarial Server.'
ms.openlocfilehash: 3474a82bfc9ed8e8bad954bb91346989d9181465
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992950"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>Habilitar la grabación de detalles de llamadas en Skype empresarial Server

**Resumen:** Obtenga información sobre cómo habilitar registros de grabación de detalles de llamadas (CDR) en Skype empresarial Server.

El registro detallado de llamadas (CDR) registra la información de uso y diagnóstico sobre actividades punto a punto, incluida la mensajería instantánea, llamadas de voz sobre IP (VoIP), uso compartido de aplicaciones, transferencia de archivos y reuniones. Los datos de uso pueden servir para calcular el retorno de la inversión y los datos de diagnóstico se pueden usar para solucionar problemas de actividades punto a punto y reuniones.

Use el procedimiento siguiente para habilitar el registro detallado de llamadas (CDR) en toda la organización o en cada sitio de la organización.

> [!NOTE]
> Para poder habilitar el CDR necesita configurar la supervisión y una base de datos de supervisión. Para más información, mire [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>Para habilitar CDR con el panel de control de Skype empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.

3. En la barra de navegación de la izquierda, haga clic en **Supervisión y archivado** y en **Registro detallado de llamadas**.

4. En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la lista, seleccione **Acción** y, luego, haga clic en **Habilitar CDR**.

    > [!NOTE]
    > CDR habilitado de forma predeterminada.

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Habilitar CDR con cmdlets de Windows PowerShell

Puede habilitar CDR mediante Windows PowerShell y el cmdlet **set-CsCdrConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype empresarial Server.

### <a name="to-enable-cdr-for-a-single-location"></a>Para habilitar CDR para una única ubicación

 Para deshabilitar CDR, establezca el parámetro EnableCDR en True ($True).

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>Para deshabilitar CDR para una única ubicación

 Para deshabilitar CDR, establezca el parámetro EnableCDR en False ($False). Esto no desinstala la supervisión, sino que pausa la recopilación y el almacenamiento de datos de CDR.

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>Utilizar un único comando para habilitar CDR en varias ubicaciones

 Este comando habilita CDR para todos los parámetros de CDR que se encuentran actualmente en uso en su organización.

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .

## <a name="see-also"></a>Vea también

[Planear la supervisión](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
