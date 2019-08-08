---
title: Configurar directivas de archivado para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar las directivas de archivado iniciales para los usuarios de Skype empresarial Server.'
ms.openlocfilehash: 4e1bf5d713201604df18db9d63c2057bfa5bb4e8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234558"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>Configurar directivas de archivado para Skype empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar las directivas de archivado iniciales para los usuarios de Skype empresarial Server.
  
En Skype empresarial Server, se usan directivas para habilitar y deshabilitar el archivado de comunicaciones internas y comunicaciones externas para los usuarios alojados en Skype empresarial Server. Entre estas directivas se incluyen:
  
- Una directiva global que se crea de forma predeterminada al implementar Skype empresarial Server
    
- Directivas de sitio opcionales, que especifican cómo se implementa el archivado para un sitio específico
    
- Directivas de nivel de usuario opcionales que especifican cómo se implementa el archivado para usuarios específicos
    
Las directivas de archivado se configuran inicialmente al implementar el archivado, pero es posible cambiar, agregar y eliminar directivas después de la implementación. En el panel de control de Skype empresarial Server, puede usar la página **Directiva** de archivado del grupo **archivado y supervisión** para administrar directivas en los niveles global, de sitio y de usuario.
  
> [!NOTE]
> Para controlar la implementación del archivado, es necesario especificar opciones, como por ejemplo, si archivar la mensajería instantánea (MI) o las conferencias, el uso del modo crítico y las opciones de purga. De manera predeterminada, no hay opciones habilitadas en la configuración del archivado global ni en ninguna otra configuración de archivado de sitio o de grupo. Es preciso especificar todas las opciones correspondientes antes de habilitar el archivado para las comunicaciones internas o externas. Para obtener más información, consulte [configurar opciones de archivado para Skype empresarial Server](configure-archiving-options.md). 
  
> [!NOTE]
> Si habilita la integración de Microsoft Exchange para su implementación, las directivas de retención local de Exchange controlan si el archivado está habilitado para los usuarios alojados en Exchange y si sus buzones se colocan en la retención local. 
  
Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía para las directivas globales, de sitio y de usuario, consulte [planear el archivado en Skype empresarial Server](../../plan-your-deployment/archiving/archiving.md). Para obtener detalles sobre cómo administrar directivas después de la implementación, consulte [Administrar directivas de archivado en Skype empresarial Server](../../manage/archiving/policies.md).
  
## <a name="global-policy"></a>Directiva global

Al implementar los servidores front-end, Skype empresarial Server crea una directiva global para el archivado. De forma predeterminada, el archivado se deshabilita en la directiva global. La directiva global controla si el archivado está habilitado para las comunicaciones internas y externas para toda la implementación, a no ser que Configure directivas de usuario o de sitio, que invaliden la directiva global, o si usa la integración de Microsoft Exchange para algunas o todas los usuarios. Si usa la integración de Microsoft Exchange, la directiva global no se aplica a los usuarios alojados en Exchange y tienen los buzones en conservación local.
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>Configurar la directiva global para archivar en bases de datos de archivado de Skype empresarial Server

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.
    
4. En la página **Directiva de archivado**, haga clic en **Global**, **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar directiva de archivado: global**, haga lo siguiente:
    
   - En **Nombre**, si no desea usar el nombre predeterminado "global", especifique un nombre nuevo para la directiva global. 
    
   - En **Descripción**, proporcione información sobre lo que es la Directiva (por ejemplo, la directiva global para *divisionName* .
    
   - Para controlar el archivado de las comunicaciones internas de todos los usuarios y sitios que no se controlan específicamente por medio de una directiva de sitio o de usuario, active o desactive la casilla **Archivar comunicaciones internas**.
    
   - Para controlar el archivado de las comunicaciones externas de todos los usuarios y sitios que no se controlan específicamente por medio de una directiva de sitio o de usuario, active o desactive la casilla **Archivar comunicaciones externas**.
    
6. Haga clic en **Confirmar**.
    
## <a name="site-policies"></a>Directivas de sitio

Puede habilitar o deshabilitar el archivado de sitios específicos si crea y configura una directiva de archivado para cada uno de esos sitios. Las directivas de sitio invalidan las directivas globales, pero las directivas de usuario invalidan las directivas de sitio. Las directivas de archivado solo se aplican si no usa la integración de Microsoft Exchange o si usa la integración de Microsoft Exchange, pero tiene algunos usuarios que no están alojados en Exchange y tienen sus buzones en conservación local.
  
### <a name="create-an-archiving-policy-for-a-site"></a>Crear una directiva de archivado para un sitio

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.
    
    Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía para las directivas globales, de sitio y de usuario, consulte [planear el archivado en Skype empresarial Server](../../plan-your-deployment/archiving/archiving.md).
    
4. Haga clic en **Nuevo** y en **Directiva de sitio**.
    
5. En **Seleccionar un sitio**, haga clic en el sitio al que se aplicará la directiva.
    
6. En **Directiva de archivado nueva**, haga lo siguiente:
    
   - En **Nombre**, especifique el nombre para la directiva de sitio. 
    
   - En **Descripción**, proporcione información sobre la directiva de sitio (por ejemplo, directiva de sitio para Redmond).
    
   - Para controlar el archivado de las comunicaciones internas para los sitios especificados, active o desactive la casilla **Archivar comunicaciones internas**.
    
   - Para controlar el archivado de las comunicaciones externas para los usuarios especificados, active o desactive la casilla **Archivar comunicaciones externas**.
    
7. Haga clic en **Confirmar**.
    
## <a name="user-policies"></a>Directivas de usuario

Puede habilitar o deshabilitar el archivado para determinados usuarios si crea y configura una directiva de archivado para usuarios y, después, aplica la directiva a usuarios o grupos de usuarios específicos. Las directivas de usuario invalidan las directivas de sitio o las directivas globales. Las directivas de archivado solo se aplican si no usa la integración de Microsoft Exchange o si usa la integración de Microsoft Exchange, pero tiene algunos usuarios que no están alojados en Exchange y tienen sus buzones en conservación local.
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>Configurar una directiva de archivado para usuarios alojados en Skype empresarial Server

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.
    
4. Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.
    
5. En **Directiva de archivado nueva**, haga lo siguiente:
    
   - En **Nombre**, escriba el nombre de la directiva de usuario. 
    
   - En **Descripción**, proporcione información sobre la directiva de usuario (por ejemplo, directiva de usuario para el departamento legal).
    
   - Para controlar el archivado de las comunicaciones internas para la directiva de usuario, active o desactive la casilla **Archivar comunicaciones internas**.
    
   - Para controlar el archivado de las comunicaciones externas para la directiva de usuario, active o desactive la casilla **Archivar comunicaciones externas**.
    
6. Haga clic en **Confirmar**.
    
Una directiva de usuario solo se aplica a los usuarios a los que asigne la directiva.
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>Aplicar una directiva de archivado de Skype empresarial Server a un usuario

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.
    
4. En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **editar el usuario de Skype empresarial Server** en **Directiva**de archivado, seleccione la Directiva de usuario de archivado que desea aplicar.
    
    > [!NOTE]
    > La ** \<configuración\> automática** aplica la configuración predeterminada de la instalación del servidor. El servidor aplica automáticamente esta configuración.
  
6. Haga clic en **Confirmar**.
    

