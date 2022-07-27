---
title: Solucionar problemas del entrenador profesional de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo solucionar problemas comunes en el Entrenador profesional para Microsoft Teams.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5ebda4324f7cc46d69b882a53684b21b4fa2932
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024195"
---
# <a name="troubleshoot-career-coach-for-microsoft-teams"></a>Solucionar problemas del entrenador profesional de Microsoft Teams

Este artículo es para administradores de TI de educación superior que necesitan solucionar problemas del Entrenador profesional para Microsoft Teams.

A continuación se muestran los problemas comunes y los pasos que los administradores de TI pueden seguir con el Entrenador profesional.

## <a name="missing-required-configuration-data"></a>Faltan datos de configuración necesarios

Si ve "Entrenador profesional se está configurando para que lo use pronto" en la experiencia del Entrenador profesional, **no se han agregado todos los datos de configuración necesarios**.

Las siguientes **secciones deben completarse** antes de que se pueda usar el Entrenador profesional:

- [Marca y preferencias](career-coach-set-up-steps.md#brand-and-preferences)
- [Conexión de LinkedIn](career-coach-set-up-steps.md#linkedin-connection)
- [Catálogo de cursos](career-coach-set-up-steps.md#course-catalog)
- [Campos de estudio](career-coach-set-up-steps.md#fields-of-study)

Haga referencia al [estado de configuración del Entrenador](career-coach-set-up-steps.md#configuration-status) profesional para ver qué opciones deben completarse.

## <a name="incorrect-formatting-of-course-catalog-or-fields-of-study-data"></a>Formato incorrecto del catálogo de cursos o campos de datos de estudio

Los CSV para el catálogo del curso y el campo de estudio requieren formatos y un tamaño máximo de 18 MB.

Haga referencia al [esquema del documento del catálogo del curso](career-coach-set-up-steps.md#course-catalog-document-format-and-schema) de Entrenador profesional y [a los campos del Entrenador profesional del esquema del documento de estudio](career-coach-set-up-steps.md#fields-of-study-document-format-and-schema) para garantizar una configuración adecuada.

Además, un archivo de catálogo de cursos no debe tener más de 15 000 filas para garantizar un procesamiento correcto.

## <a name="missing-fields-in-career-coach-settings-pages"></a>Faltan campos en las páginas de configuración del Entrenador profesional

Las páginas de configuración de Entrenador profesional tienen campos obligatorios. Si no se han completado los campos necesarios, la página no se enviará.

Es posible que no vea un mensaje de advertencia y que la página no se envíe.

El envío se realiza correctamente cuando aparece un banner verde en la parte superior de la página.

## <a name="setup-policy-changes-arent-complete"></a>No se han completado los cambios de la directiva de configuración

Si el Entrenador profesional no se muestra en Microsoft Teams para los usuarios, es posible que los cambios en la directiva de configuración aún no se hayan aplicado. El Entrenador profesional no se instalará ni anclará para los usuarios en Microsoft Teams hasta que se apliquen los cambios en la directiva de configuración. Los cambios de directiva pueden tardar unas horas en surtir efecto.

Sin embargo, el Entrenador profesional se puede instalar directamente desde la tienda de aplicaciones de Microsoft Teams.

- Si los usuarios no pueden encontrar entrenador profesional en la tienda de aplicaciones de Microsoft Teams, revise las directivas de permisos de la aplicación y asegúrese de que el Entrenador profesional no sea una aplicación bloqueada.
- Entrenador profesional es una aplicación de Microsoft y es recomendable permitir las aplicaciones de Microsoft por directivas de permisos. Obtenga más información sobre [cómo configurar directivas de permisos](teams-app-permission-policies.md).

## <a name="career-coach-initialization-isnt-complete"></a>La inicialización del Entrenador profesional no está completa

Es posible que se produzca el siguiente error: "No podemos recuperar la configuración de la aplicación. Inténtelo de nuevo. Si sigues teniendo problemas, ponte en contacto con el servicio de atención al cliente de Microsoft".

Compruebe el **estado aprovisionamiento del servicio** en la [página de configuración de Entrenador profesional](career-coach-set-up-steps.md#career-coach-settings-status).

Si el espacio empresarial aún se está inicializando, espere 15 minutos y vuelva a intentarlo. Abra un vale de soporte técnico si sigue recibiendo el error.
