---
title: Aplicar una directiva de archivado a los usuarios de Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Resumen: Conozca cómo asignar una directiva de archivado para los usuarios de Skype para Business Server 2015.'
ms.openlocfilehash: fc9811aa57a1ba397dedce325f03ea2d77e4413b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server-2015"></a>Aplicar una directiva de archivado a los usuarios de Skype Empresarial Server 2015

**Resumen:** Obtenga información acerca de cómo asignar una directiva de archivado para los usuarios de Skype para Business Server 2015.
  
Si ha creado uno o más de las directivas de usuario para el archivado de los usuarios alojados en Skype para Business Server 2015, puede implementar soporte de archiving para usuarios específicos mediante la aplicación de las políticas adecuadas para los usuarios o grupos de usuarios. Por ejemplo, si crea una directiva para admitir el archivado de comunicaciones internas, puede aplicarlo al menos un usuario o grupo de usuarios para soportar archiving de Skype del usuario para las comunicaciones de negocios servidor 2015.
  
> [!NOTE]
> Si habilita la integración de Microsoft Exchange para la implementación de Exchange en el mismo lugar mantenga control de directivas si el archivado está habilitado para los usuarios que están alojados en Exchange y han puesto a sus buzones en mantener en el lugar. Para obtener más información, vea [planear para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md) y [Configurar la integración con almacenamiento de información de Exchange para Skype para Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Aplicar una directiva de usuario con el Panel de control

Para aplicar una directiva de usuario con el Panel de control:
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar. 
    
4. En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar usuario de Lync Server** , bajo **Directiva de archivado**, seleccione la directiva de usuario de archivado que desee aplicar.
    
    > [!NOTE]
    > La ** \<automática\> ** configuración aplica la configuración predeterminada de instalación del servidor. El servidor aplica esta configuración automáticamente.
  
6. Haga clic en **Confirmar**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Aplicar una directiva de usuario mediante Windows PowerShell

También puede aplicar una directiva de usuario mediante el cmdlet de Windows PowerShell **Grant CsArchivingPolicy** .
  
El siguiente comando permite asignar la directiva de archivado por usuario RedmondArchivingPolicy al usuario Ken Myer.
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Este comando asigna el usuario por directiva RedmondArchivingPolicy a todos los usuarios de archivado que hayan cuentas alojados en el grupo registrador atl-cs-001.contoso.com. Para obtener más información acerca del parámetro de filtro utilizado en este comando, consulte la documentación del cmdlet [Get-Csusuario](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

```

El siguiente comando quita cualquier directiva de archivado por usuario previamente asignada a Ken Myer. Una vez quitada la directiva por usuario, Ken Myer pasará automáticamente a ser administrado con la directiva global (o, de existir, por la directiva de su sitio local). Las directivas de sitio tienen prioridad sobre las directivas globales.
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Para obtener más información, consulte la documentación de cmdlet de [Concesión CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .
  

