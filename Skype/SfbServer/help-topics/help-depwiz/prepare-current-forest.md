---
title: Preparar bosque actual
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Para preparar el bosque de los servicios de dominio de Active Directory, debe extender correctamente el esquema, como se describe en el tema ejecución de la preparación del esquema y asegurarse de que el esquema se ha replicado.
ms.openlocfilehash: d13660eb703a793c1fc59ed422bd0b317986a86b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823534"
---
# <a name="prepare-current-forest"></a>Preparar bosque actual

Para preparar el bosque de los servicios de dominio de Active Directory, debe extender correctamente el esquema, como se describe en el tema ejecución de la [preparación del esquema](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)y asegurarse de que el esquema se ha replicado.

Una vez completados los requisitos previos, puede empezar el **Paso 3: Preparar el bosque actual**. Para preparar el bosque, inicie sesión en un equipo de la raíz del bosque como miembro del grupo Admins. del dominio en la raíz del bosque, o bien como miembro del grupo Administradores de organización del bosque que se prepara.

1. En el Asistente para la implementación, en el **Paso 3: Preparar bosque actual**, haga clic en **Ejecutar**.

2. En la página **Preparar el bosque**, haga clic en **Siguiente**.

    > [!NOTE]
    > La preparación del bosque le permite elegir dónde ubicar los grupos universales para Skype empresarial Server 2015. Elija una ubicación que respete los requisitos de su organización.

3. En la página **Ejecución de comandos**, busque **Estado de tarea: Completado** y haga clic en **Ver registro**. Asegúrese de que no haya errores. Examine las advertencias para saber si son las previstas y son habituales en la infraestructura.

4. En la columna **acción** del registro, expanda **preparación del bosque**, busque un ** \<resultado\> ** de ejecución correcta al final de cada tarea para comprobar que la preparación del bosque se completó correctamente, cierre el registro y, a continuación, haga clic en **Finalizar**.

5. Espere a que se complete la replicación de servicios de dominio de Active Directory, o fuerce la replicación en todos los controladores de dominio que aparecen en el complemento **sitios y servicios de Active** Directory para el controlador de dominio raíz del bosque, antes de ejecutar la preparación del dominio. Fuerce la replicación entre los controladores de dominio de todos los sitios de Active Directory para que la replicación dentro de los sitios se produzca en minutos.

    > [!TIP]
    > Si necesita revisar los archivos de registro creados por el Asistente para la implementación de Skype empresarial Server, puede encontrarlos en el equipo en el que se ejecutó el Asistente para la implementación, en el directorio usuarios del usuario de los servicios de dominio de Active Directory que ejecutó el paso. Por ejemplo, si el usuario ha iniciado sesión como administrador del dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp


