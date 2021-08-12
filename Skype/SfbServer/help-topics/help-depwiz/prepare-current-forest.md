---
title: Preparar bosque actual
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Para preparar el bosque de Servicios de dominio de Active Directory, debe extender correctamente el esquema, tal como se describe en el tema Running Schema Preparation, y asegurarse de que el esquema se haya replicado.
ms.openlocfilehash: 6b02ae0139c4ac813dd8562b237022112f76201d79e82b856e5bfe7e8d6972e7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309655"
---
# <a name="prepare-current-forest"></a>Preparar bosque actual

Para preparar el bosque de Servicios de dominio de Active Directory, debe extender correctamente el esquema, tal como se describe en el tema [Running Schema Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema), y asegurarse de que el esquema se haya replicado.

Después de completar estos requisitos previos, puede comenzar **el paso 3: Preparar el bosque actual**. Para preparar el bosque, inicie sesión en un equipo de la raíz del bosque como miembro de administradores de dominio en la raíz del bosque o como miembro de los administradores de Enterprise para el bosque que está preparando.

1. En el Asistente para implementación **del paso 3: Preparar el bosque actual,** haga clic **en Ejecutar**.

2. En la página **Preparar bosque,** haga clic **en Siguiente**.

    > [!NOTE]
    > Preparación del bosque permite elegir dónde colocar los grupos universales para Skype Empresarial Server 2015. Elija una ubicación que respete los requisitos de su organización.

3. En la página **Ejecución de comandos**, busque **Estado de la tarea: completado** y, a continuación, haga clic en **Ver registro**. Asegúrese de que no hay errores. Revise las advertencias para determinar si se esperan y son típicas para la infraestructura.

4. En  la columna Acción del registro, expanda Forest **Prep**, busque un resultado de ejecución al final de cada tarea para comprobar que la preparación del bosque se completó correctamente, cierre el registro y, a continuación, haga clic en **\<Success\>** **Finalizar**.

5. Espere a que se complete la replicación de Servicios de dominio de Active Directory o forzar la replicación a todos los controladores de dominio enumerados en el complemento Sitios y servicios de **Active Directory** para el controlador de dominio raíz del bosque, antes de ejecutar la preparación del dominio. Fuerce la replicación entre los controladores de dominio en todos los sitios de Active Directory para que la replicación en los sitios se produzca en cuestión de minutos.

    > [!TIP]
    > Si necesita revisar los archivos de registro creados por el Asistente para la implementación de Skype Empresarial Server, puede encontrarlos en el equipo donde se ejecutó el Asistente para implementación, en el directorio Usuarios del usuario de Servicios de dominio de Active Directory que ejecutó el paso. Por ejemplo, si el usuario inició sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp