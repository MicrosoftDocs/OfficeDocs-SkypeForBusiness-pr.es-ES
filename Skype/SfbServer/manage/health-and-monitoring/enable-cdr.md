---
title: Habilitar el registro de detalles de llamada de Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Resumen: Obtenga información sobre cómo habilitar detalles de llamadas (CDR) registros en Skype para Business Server.'
ms.openlocfilehash: 55fafd037e271166eaf94b460f656b811720e00f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20995744"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>Habilitar el registro de detalles de llamada de Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo habilitar detalles de llamadas (CDR) registros en Skype para Business Server.
  
El registro detallado de llamadas (CDR) registra la información de uso y diagnóstico sobre actividades punto a punto, incluida la mensajería instantánea, llamadas de voz sobre IP (VoIP), uso compartido de aplicaciones, transferencia de archivos y reuniones. Los datos de uso pueden servir para calcular el retorno de la inversión y los datos de diagnóstico se pueden usar para solucionar problemas de actividades punto a punto y reuniones. 
  
Use el procedimiento siguiente para habilitar el registro detallado de llamadas (CDR) en toda la organización o en cada sitio de la organización.
  
> [!NOTE]
> Para poder habilitar el CDR necesita configurar la supervisión y una base de datos de supervisión. Para obtener información detallada, vea [Implementación de supervisión](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx). 
  
### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>Para habilitar el Panel de Control de servidor empresarial CDR con Skype

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
    
3. En la barra de navegación de la izquierda, haga clic en **Supervisión y archivado** y en **Registro detallado de llamadas**. 
    
4. En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la lista, seleccione **Acción** y, luego, haga clic en **Habilitar CDR**.
    
    > [!NOTE]
    > CDR habilitado de forma predeterminada. 
  
## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Habilitación de CDR mediante el uso de cmdlets de Windows PowerShell

Puede habilitar a CDR mediante Windows PowerShell y el cmdlet **Set-CsCdrConfiguration** . Se puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-enable-cdr-for-a-single-location"></a>Para habilitar CDR para una única ubicación

 Para deshabilitar CDR, establezca el parámetro EnableCDR en True ($True).
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>Para deshabilitar CDR para una única ubicación

 Para deshabilitar CDR, establezca el parámetro EnableCDR en False ($False). Esto no desinstala la supervisión, sino que pausa la recopilación y el almacenamiento de datos de CDR.
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>Utilizar un único comando para habilitar CDR en varias ubicaciones

 Este comando habilita CDR para todos los parámetros de CDR que se encuentran actualmente en uso en su organización.
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True
  ```

Para obtener más información, vea el tema de ayuda para el cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>Vea también

[Planeación de la supervisión](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)
  
[Implementación de la supervisión](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)