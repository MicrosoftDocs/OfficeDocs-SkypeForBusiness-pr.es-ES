---
title: Configurar las directivas de archivado de Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Resumen: Leer este tema para aprender a configurar políticas de archiving iniciales de Skype para los usuarios de Business Server 2015.'
ms.openlocfilehash: 9829d0c5ad5ea9e62c2335c3387fcd22623c6751
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-policies-for-skype-for-business-server-2015"></a>Configurar las directivas de archivado de Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para aprender a configurar políticas de archiving iniciales de Skype para los usuarios de Business Server 2015.
  
En Skype para Business Server, utilice las directivas para habilitar y deshabilitar el archivado de comunicaciones internas y comunicaciones externas para los usuarios que están alojados en Skype para Business Server. Entre estas directivas se incluyen:
  
- Una directiva global que por defecto se crea al implementar Skype para Business Server
    
- Directivas de sitio opcionales, que especifican cómo se implementa el archivado para un sitio específico
    
- Políticas a nivel de usuario opcionales que especifican cómo se implementa el archivado para usuarios específicos
    
Las directivas de archivado se configuran inicialmente al implementar el archivado, pero es posible cambiar, agregar y eliminar directivas después de la implementación. En Skype para Panel de Control de servidor empresarial, puede utilizar la página de **Directivas de archivado** del grupo **Archiving y supervisión** para administrar las políticas a nivel global, sitio y niveles de usuario.
  
> [!NOTE]
> Para controlar la implementación del archivado, es necesario especificar opciones, como por ejemplo, si archivar la mensajería instantánea (MI) o las conferencias, el uso del modo crítico y las opciones de purga. De manera predeterminada, no hay opciones habilitadas en la configuración del archivado global ni en ninguna otra configuración de archivado de sitio o de grupo. Es preciso especificar todas las opciones correspondientes antes de habilitar el archivado para las comunicaciones internas o externas. Para obtener información detallada, vea [Configurar opciones de Skype para Business Server 2015 de archiving](configure-archiving-options.md). 
  
> [!NOTE]
> Si habilita la integración de Microsoft Exchange para la implementación de Exchange en el mismo lugar mantenga control de directivas si el archivado está habilitado para los usuarios que están alojados en Exchange y han puesto a sus buzones en mantener en el lugar. 
  
Para obtener más información acerca de las políticas de archiving cómo funciona, incluida la jerarquía global, sitio, y las directivas de usuario, consulte [Plan para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md). Para obtener más información acerca de cómo administrar las directivas después de la implementación, vea [administrar políticas de archiving en Skype para Business Server 2015](../../manage/archiving/policies.md).
  
## <a name="global-policy"></a>Directiva global

Al implementar los servidores frontales, Skype para Business Server crea una política global para archiving. De forma predeterminada, el archivado se deshabilita en la directiva global. La directiva global controla si el archivado está habilitado para las comunicaciones internas y externas para toda la implementación, a menos que configure directivas de sitio o usuario, que reemplaza la directiva global, o si utiliza la integración de Microsoft Exchange para algunos o todos de los usuarios. Si utiliza la integración de Microsoft Exchange, la directiva global no se aplica a todos los usuarios que están alojados en Exchange y disponer los buzones en posesión en el lugar.
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>Configurar la directiva global para archivado de Skype para bases de datos de archivado de Business Server

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.
    
4. En la página **Directiva de archivado**, haga clic en **Global**, **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar directiva de archivado: global**, haga lo siguiente:
    
   - En **Nombre**, si no desea usar el nombre predeterminado "global", especifique un nombre nuevo para la directiva global. 
    
   - En **Descripción**, proporcione información acerca de la directiva (por ejemplo, la directiva Global para *divisionName* .
    
   - Para controlar el archivado de las comunicaciones internas de todos los usuarios y sitios que no se controlan específicamente por medio de una directiva de sitio o de usuario, active o desactive la casilla **Archivar comunicaciones internas**.
    
   - Para controlar el archivado de las comunicaciones externas de todos los usuarios y sitios que no se controlan específicamente por medio de una directiva de sitio o de usuario, active o desactive la casilla **Archivar comunicaciones externas**.
    
6. Haga clic en **Confirmar**.
    
## <a name="site-policies"></a>Directivas de sitio

Puede habilitar o deshabilitar el archivado de sitios específicos si crea y configura una directiva de archivado para cada uno de esos sitios. Las directivas de sitio invalidan las directivas globales, pero las directivas de usuario invalidan las directivas de sitio. Políticas de archiving sólo se aplican si no se utiliza la integración de Microsoft Exchange o, si utiliza la integración de Microsoft Exchange, pero han puesto a algunos usuarios que no están alojados en Exchange y tienen sus buzones en mantenga In situ.
  
### <a name="create-an-archiving-policy-for-a-site"></a>Crear una directiva de archivado para un sitio

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.
    
    Para obtener más información acerca de las políticas de archiving cómo funciona, incluida la jerarquía global, sitio, y las directivas de usuario, consulte [Plan para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md).
    
4. Haga clic en **Nuevo** y en **Directiva de sitio**.
    
5. En **Seleccionar un sitio**, haga clic en el sitio al que se aplicará la directiva.
    
6. En **Directiva de archivado nueva**, haga lo siguiente:
    
   - En **Nombre**, especifique el nombre para la directiva de sitio. 
    
   - En **Descripción**, proporcione información sobre la directiva de sitio (por ejemplo, directiva de sitio para Redmond).
    
   - Para controlar el archivado de las comunicaciones internas para los sitios especificados, active o desactive la casilla **Archivar comunicaciones internas**.
    
   - Para controlar el archivado de las comunicaciones externas para los usuarios especificados, active o desactive la casilla **Archivar comunicaciones externas**.
    
7. Haga clic en **Confirmar**.
    
## <a name="user-policies"></a>Directivas de usuario

Puede habilitar o deshabilitar el archivado para determinados usuarios si crea y configura una directiva de archivado para usuarios y, después, aplica la directiva a usuarios o grupos de usuarios específicos. Las directivas de usuario invalidan las directivas de sitio o las directivas globales. Políticas de archiving sólo se aplican si no se utiliza la integración de Microsoft Exchange o, si utiliza la integración de Microsoft Exchange, pero han puesto a algunos usuarios que no están alojados en Exchange y tienen sus buzones en mantenga In situ.
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>Configurar una directiva de archivado para usuarios alojados en Skype para Business Server

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.
    
4. Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.
    
5. En **Directiva de archivado nueva**, haga lo siguiente:
    
   - En **Nombre**, escriba el nombre de la directiva de usuario. 
    
   - En **Descripción**, proporcione información sobre la directiva de usuario (por ejemplo, directiva de usuario para el departamento legal).
    
   - Para controlar el archivado de las comunicaciones internas para la directiva de usuario, active o desactive la casilla **Archivar comunicaciones internas**.
    
   - Para controlar el archivado de las comunicaciones externas para la directiva de usuario, active o desactive la casilla **Archivar comunicaciones externas**.
    
6. Haga clic en **Confirmar**.
    
Una directiva de usuario solo se aplica a los usuarios a los que asigne la directiva.
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>Aplicar un Skype para Business Server directiva a un usuario de archivado

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.
    
4. En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar Skype para usuario Business Server** bajo **Directiva de archivado**, seleccione la directiva de usuario de archivado que desee aplicar.
    
    > [!NOTE]
    > La ** \<automática\> ** configuración aplica la configuración predeterminada de instalación del servidor. El servidor aplica esta configuración automáticamente.
  
6. Haga clic en **Confirmar**.
    

