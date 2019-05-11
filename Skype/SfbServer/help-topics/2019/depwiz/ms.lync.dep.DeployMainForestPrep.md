---
title: Preparar bosque actual
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: Para preparar el bosque de los servicios de dominio de Active Directory, debe correctamente extender el esquema, como se describe en el tema preparación del esquema de ejecución y asegúrese de que el esquema se ha replicado.
ms.openlocfilehash: 5cf217e054f513b8e3fcbc203cf4c0d76719e7cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893696"
---
# <a name="prepare-current-forest"></a>Preparar bosque actual

Para preparar el bosque de los servicios de dominio de Active Directory, debe correctamente extender el esquema, como se describe en el tema [Preparación del esquema de ejecución](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)y asegúrese de que el esquema se ha replicado.

Una vez completados los requisitos previos, puede empezar el **Paso 3: Preparar el bosque actual**. Para preparar el bosque, inicie sesión en un equipo de la raíz del bosque como miembro del grupo Admins. del dominio en la raíz del bosque, o bien como miembro del grupo Administradores de organización del bosque que se prepara.

1. En el Asistente para la implementación, en el **Paso 3: Preparar bosque actual**, haga clic en **Ejecutar**.

2. En la página **Preparar el bosque**, haga clic en **Siguiente**.

    > [!NOTE]
    > La preparación del bosque permite elegir dónde desea colocar los grupos universales de Skype para Business Server. Elija una ubicación que respete los requisitos de su organización.

3. En la página **Ejecución de comandos**, busque **Estado de tarea: Completado** y haga clic en **Ver registro**. Asegúrese de que no haya errores. Examine las advertencias para saber si son las previstas y son habituales en la infraestructura.

4. En la columna **acción** en el registro, expanda **Preparar el bosque**, busque un ** \<éxito\> ** resultado de ejecución al final de cada tarea para comprobar que la preparación del bosque se realizó correctamente, cierre el registro y, a continuación, haga clic en **Finalizar **.

5. Espere a completar la replicación de los servicios de dominio de Active Directory o fuerce la replicación en todos los controladores de dominio enumerados en el complemento **servicios y sitios de Active Directory** para el controlador de dominio raíz de bosque, antes de ejecutar la preparación del dominio. Forzar la replicación entre los controladores de dominio en todos los sitios de Active Directory para que la replicación dentro de los sitios que se produzca en cuestión de minutos.

    > [!TIP]
    > Si necesita revisar los archivos de registro que se crean mediante la Skype para el Asistente para la implementación de Business Server, se puede encontrar en el equipo donde se ejecutó el Asistente para la implementación, en el directorio de usuarios del usuario de los servicios de dominio de Active Directory que se ejecutó el paso. Por ejemplo, si el usuario iniciado sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp


