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
description: 'Resumen: lea este tema para obtener información sobre cómo configurar directivas de archivado iniciales para usuarios de Skype Empresarial Server.'
ms.openlocfilehash: ab737305561aa20c873bbce6e0f075d17fedd0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820860"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>Configurar directivas de archivado para Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar directivas de archivado iniciales para usuarios de Skype Empresarial Server.
  
En Skype Empresarial Server, se usan directivas para habilitar y deshabilitar el archivado para comunicaciones internas y externas para los usuarios que están en Skype Empresarial Server. Esto incluye lo siguiente:
  
- Una directiva global que se crea de forma predeterminada al implementar Skype Empresarial Server
    
- Directivas de nivel de sitio opcionales que especifican cómo se implementa el archivado para un sitio específico
    
- Directivas opcionales de nivel de usuario que especifican cómo se implementa el archivado para usuarios específicos
    
Las directivas de archivado se establecen inicialmente al implementar el archivado, pero puede cambiar, agregar y eliminar directivas después de la implementación. En el Panel de control de  Skype Empresarial Server, puede usar la página Directiva de archivado del grupo de archivado y supervisión para administrar directivas en los niveles global, de sitio y de usuario. 
  
> [!NOTE]
> Para controlar la implementación del archivado, debe especificar opciones, como archivar mensajería instantánea o conferencias, el uso del modo crítico y las opciones de depuración. De forma predeterminada, no hay opciones habilitadas en la configuración de archivado global ni en ninguna configuración de archivado de sitio o grupo de servidores. Debe especificar todas las opciones adecuadas antes de habilitar el archivado para las comunicaciones internas o externas. Para obtener más información, [consulte Configurar las opciones de archivado para Skype Empresarial Server.](configure-archiving-options.md) 
  
> [!NOTE]
> Si habilita la integración de Microsoft Exchange para su implementación, las directivas de retención de Exchange In-Place controlan si el archivado está habilitado para los usuarios que están en Exchange y tienen sus buzones en retención In-Place local. 
  
Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, de sitio y de usuario, consulte [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md). Para obtener más información sobre cómo administrar directivas después de la implementación, consulte Administrar directivas [de archivado en Skype Empresarial Server.](../../manage/archiving/policies.md)
  
## <a name="global-policy"></a>Directiva global

Al implementar los servidores front-end, Skype Empresarial Server crea una directiva global para el archivado. De forma predeterminada, el archivado está deshabilitado en la directiva global. La directiva global controla si el archivado está habilitado para comunicaciones internas y externas para toda la implementación, a menos que configure directivas de sitio o de usuario, que invalidan la directiva global, o si usa la integración de Microsoft Exchange para algunos o todos los usuarios. Si usa la integración de Microsoft Exchange, la directiva global no se aplica a ningún usuario que se encuentra en Exchange y que tiene los buzones en retención In-Place local.
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>Configurar la directiva global de archivado para las bases de datos de archivado de Skype Empresarial Server

1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.
    
4. En la página **Directiva de** archivado, haga clic **en Global**, **Editar** y, a continuación, en **Mostrar detalles.**
    
5. En **Editar directiva de archivado - Global**, haga lo siguiente:
    
   - En **Nombre**, si no desea usar el nombre predeterminado de Global, especifique un nombre nuevo para la directiva global. 
    
   - En **Descripción,** proporcione información sobre cuál es la directiva (por ejemplo, Directiva global para  *divisionName*  .
    
   - Para controlar el archivado de las comunicaciones internas de todos los usuarios y sitios que no se controlan específicamente mediante una directiva de sitio o de usuario, active o desactive la casilla **Archivar comunicaciones internas**.
    
   - Para controlar el archivado de comunicaciones externas para todos los sitios y usuarios que no se controlan específicamente a través de una directiva de sitio o directiva de usuario, active o desactive la casilla Archivar **comunicaciones** externas.
    
6. Haga clic en **Confirmar**.
    
## <a name="site-policies"></a>Directivas del sitio

Puede habilitar o deshabilitar el archivado para sitios específicos mediante la creación de una directiva de archivado para cada uno de esos sitios. Las directiva de sitio anulan la directiva global pero las directivas de usuario anulan las directivas de sitio. Las directivas de archivado solo se aplican si no usa la integración de Microsoft Exchange o, si usa la integración de Microsoft Exchange, pero tiene algunos usuarios que no están en Exchange y tienen sus buzones en retención In-Place local.
  
### <a name="create-an-archiving-policy-for-a-site"></a>Crear una directiva de archivado para un sitio

1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.
    
    Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, de sitio y de usuario, consulte [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).
    
4. Haga clic en  **Nuevo** y en  **Directiva de sitio**.
    
5. En  **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.
    
6. En  **Directiva de archivado nueva**, haga lo siguiente:
    
   - En  **Nombre**, especifique el nombre para la directiva de sitio. 
    
   - En **Descripción**, proporcione información sobre la función de la directiva de sitio (por ejemplo, directiva de archivado de usuarios externos para Redmond).
    
   - Para controlar el archivado de comunicaciones internas para los sitios especificados, active o desactive la casilla  **Archivar comunicaciones internas**.
    
   - Para controlar el archivado de comunicaciones externas para los usuarios especificados, active o desactive la casilla  **Archivar comunicaciones externas**.
    
7. Haga clic en  **Confirmar**.
    
## <a name="user-policies"></a>Directivas de usuario

Puede habilitar o deshabilitar el archivado para usuarios específicos creando y configurando una directiva de archivado para usuarios y, a continuación, aplicando la directiva a usuarios o grupos de usuarios específicos. Las directivas de usuario invalidan cualquier directiva global o de sitio. Las directivas de archivado solo se aplican si no usa la integración de Microsoft Exchange o, si usa la integración de Microsoft Exchange, pero tiene algunos usuarios que no están en Exchange y tienen sus buzones en retención In-Place local.
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>Configurar una directiva de archivado para los usuarios que están en Skype Empresarial Server

1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.
    
4. Haga clic en **Nuevo** y en **Directiva de usuario**.
    
5. En **Nueva directiva de archivado**, haga lo siguiente:
    
   - En **Nombre**, escriba el nombre de la directiva de usuario. 
    
   - En **Descripción**, proporcione información sobre cuál es la directiva de usuario (por ejemplo, directiva de usuario para el departamento legal).
    
   - Para controlar el archivado de las comunicaciones internas para la directiva de usuario, seleccione o anule la selección de la casilla de verificación **Archivar comunicaciones internas**.
    
   - Para controlar el archivado de las comunicaciones externas para la directiva de usuario, seleccione o anule la selección de la casilla de verificación **Archivar comunicaciones externas**.
    
6. Haga clic en **Confirmar**.
    
Una directiva de usuario solo se aplica a los usuarios a los que asigne la directiva.
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>Aplicar una directiva de archivado de Skype Empresarial Server a un usuario

1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Usuarios** y, a continuación, busque la cuenta de usuario que quiera configurar.
    
4. En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, a continuación, en **Mostrar detalles**.
    
5. En **Editar usuario de Skype Empresarial Server** en la directiva **de** archivado, seleccione la directiva de usuario de archivado que desee aplicar.
    
    > [!NOTE]
    > La **\<Automatic\>** configuración aplica la configuración de instalación predeterminada del servidor. Esta configuración se aplica automáticamente por el servidor.
  
6. Haga clic en **Confirmar**.
    

