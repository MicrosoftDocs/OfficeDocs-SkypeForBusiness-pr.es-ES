---
title: Configurar directivas de archivado para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Resumen: lea este tema para obtener información sobre cómo configurar directivas de archivado iniciales para Skype Empresarial Server usuarios.'
ms.openlocfilehash: 9db20eefd26de31eb01ab25d4ef7596319459b68be3f76ce95ba0b355122eee8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312128"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>Configurar directivas de archivado para Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar directivas de archivado iniciales para Skype Empresarial Server usuarios.
  
En Skype Empresarial Server, se usan directivas para habilitar y deshabilitar el archivado de comunicaciones internas y externas para usuarios que se encuentran en Skype Empresarial Server. Esto incluye lo siguiente:
  
- Una directiva global que se crea de forma predeterminada al implementar Skype Empresarial Server
    
- Directivas de nivel de sitio opcionales que especifican cómo se implementa el archivado para un sitio específico
    
- Directivas opcionales de nivel de usuario que especifican cómo se implementa el archivado para usuarios específicos
    
Inicialmente, configura directivas de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar directivas después de la implementación. En Skype Empresarial Server panel de control, puede  usar la  página Directiva de archivado del grupo Archivado y supervisión para administrar directivas en los niveles global, de sitio y de usuario.
  
> [!NOTE]
> Para controlar la implementación del archivado, debe especificar opciones, como archivar mensajería instantánea o conferencia, el uso del modo crítico y opciones de depuración. De forma predeterminada, no hay opciones habilitadas en la configuración de archivado global ni en ninguna configuración de archivado de sitio o grupo. Debe especificar todas las opciones adecuadas antes de habilitar el archivado para comunicaciones internas o externas. Para obtener más información, vea [Configure archiving options for Skype Empresarial Server](configure-archiving-options.md). 
  
> [!NOTE]
> Si habilita la integración de Microsoft Exchange para la implementación, las directivas de retención de Exchange In-Place controlan si el archivado está habilitado para los usuarios que se encuentran en Exchange y tienen sus buzones en retención In-Place. 
  
Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, de sitio y de usuario, vea [Plan for archiving in Skype Empresarial Server](../../plan-your-deployment/archiving/archiving.md). Para obtener más información acerca de cómo administrar directivas después de la implementación, vea [Manage archiving policies in Skype Empresarial Server](../../manage/archiving/policies.md).
  
## <a name="global-policy"></a>Directiva global

Al implementar los servidores front-end, Skype Empresarial Server crea una directiva global para el archivado. De forma predeterminada, el archivado está deshabilitado en la directiva global. La directiva global controla si el archivado está habilitado para comunicaciones internas y externas para toda la implementación, a menos que configure directivas de sitio o de usuario, que invalide la directiva global, o si usa la integración de Microsoft Exchange para algunos o todos los usuarios. Si usa la integración de Microsoft Exchange, la directiva global no se aplica a los usuarios que se encuentran en Exchange y tienen los buzones en In-Place retención.
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>Configurar la directiva global de archivado para bases Skype Empresarial Server de archivado

1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 
    
3. En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.
    
4. En la página **Directiva de archivado,** haga clic en **Global**, haga clic **en Editar** y, a continuación, haga clic en **Mostrar detalles.**
    
5. En **Editar directiva de archivado - Global**, haga lo siguiente:
    
   - En **Nombre**, si no desea usar el nombre predeterminado de Global, especifique un nuevo nombre para la directiva global. 
    
   - En **Descripción**, proporcione información sobre lo que es la directiva (por ejemplo, Directiva global para  *divisionName*  .
    
   - Para controlar el archivado de las comunicaciones internas de todos los usuarios y sitios que no se controlan específicamente mediante una directiva de sitio o de usuario, active o desactive la casilla **Archivar comunicaciones internas**.
    
   - Para controlar el archivado de comunicaciones externas para todos los sitios y usuarios no controlados específicamente a través de una directiva de sitio o directiva de usuario, active o desactive la casilla Archivar **comunicaciones** externas.
    
6. Haga clic en **Confirmar**.
    
## <a name="site-policies"></a>Directivas del sitio

Puede habilitar o deshabilitar el archivado para sitios específicos mediante la creación de una directiva de archivado para cada uno de esos sitios. Las directiva de sitio anulan la directiva global pero las directivas de usuario anulan las directivas de sitio. Las directivas de archivado solo se aplican si no usa la integración de Microsoft Exchange o, si usa la integración de Microsoft Exchange, pero tiene algunos usuarios que no están en Exchange y tienen sus buzones en retención In-Place.
  
### <a name="create-an-archiving-policy-for-a-site"></a>Crear una directiva de archivado para un sitio

1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control.
    
3. En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.
    
    Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, de sitio y de usuario, vea [Plan for archiving in Skype Empresarial Server](../../plan-your-deployment/archiving/archiving.md).
    
4. Haga clic en  **Nuevo** y en  **Directiva de sitio**.
    
5. En  **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.
    
6. En  **Directiva de archivado nueva**, haga lo siguiente:
    
   - En  **Nombre**, especifique el nombre para la directiva de sitio. 
    
   - En **Descripción**, proporcione información sobre la función de la directiva de sitio (por ejemplo, directiva de archivado de usuarios externos para Redmond).
    
   - Para controlar el archivado de comunicaciones internas para los sitios especificados, active o desactive la casilla  **Archivar comunicaciones internas**.
    
   - Para controlar el archivado de comunicaciones externas para los usuarios especificados, active o desactive la casilla  **Archivar comunicaciones externas**.
    
7. Haga clic en  **Confirmar**.
    
## <a name="user-policies"></a>Directivas de usuario

Para habilitar o deshabilitar el archivado para usuarios específicos, cree y configure una directiva de archivado para los usuarios y, a continuación, aplique la directiva a usuarios o grupos de usuarios específicos. Las directivas de usuario invalidan cualquier directiva global o directivas de sitio. Las directivas de archivado solo se aplican si no usa la integración de Microsoft Exchange o, si usa la integración de Microsoft Exchange, pero tiene algunos usuarios que no están en Exchange y tienen sus buzones en retención In-Place.
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>Configurar una directiva de archivado para los usuarios que se alo Skype Empresarial Server

1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 
    
3. En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.
    
4. Haga clic en **Nuevo** y en **Directiva de usuario**.
    
5. En **Nueva directiva de archivado**, haga lo siguiente:
    
   - En **Nombre**, escriba el nombre de la directiva de usuario. 
    
   - En **Descripción**, proporcione información sobre cuál es la directiva de usuario (por ejemplo, directiva de usuario para el departamento legal).
    
   - Para controlar el archivado de las comunicaciones internas para la directiva de usuario, seleccione o anule la selección de la casilla de verificación **Archivar comunicaciones internas**.
    
   - Para controlar el archivado de las comunicaciones externas para la directiva de usuario, seleccione o anule la selección de la casilla de verificación **Archivar comunicaciones externas**.
    
6. Haga clic en **Confirmar**.
    
Una directiva de usuario solo se aplica a los usuarios a los que asigne la directiva.
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>Aplicar una directiva Skype Empresarial Server de archivado a un usuario

1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 
    
3. En la barra de navegación izquierda, haga clic en **Usuarios** y, a continuación, busque la cuenta de usuario que quiera configurar.
    
4. En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, a continuación, en **Mostrar detalles**.
    
5. En **Editar Skype Empresarial Server usuario en** Directiva de **archivado,** seleccione la directiva de usuario de archivado que desea aplicar.
    
    > [!NOTE]
    > La **\<Automatic\>** configuración aplica la configuración predeterminada de instalación del servidor. Esta configuración se aplica automáticamente por el servidor.
  
6. Haga clic en **Confirmar**.
    

