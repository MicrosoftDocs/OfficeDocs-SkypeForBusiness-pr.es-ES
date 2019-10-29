---
title: 'Aplicación de pacientes para administradores de equipos '
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto: Microsoft Teams
ms.reviewer: anach
description: Aplicación de pacientes para administradores de equipos
ms.openlocfilehash: 1ed3efc1aa5a6d3eb4554fca6ee3bd7cfe57f4c0
ms.sourcegitcommit: 25b6bf2c3050390cd668d2495ffcf31c44d0ff62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2019
ms.locfileid: "37749562"
---
# <a name="patients-app-overview"></a>Información general de la aplicación de pacientes

La aplicación patients es una aplicación de la tienda Microsoft teams que está disponible para todos los usuarios de Teams. La aplicación permite que los equipos de cuidados de pacientes compuestos por trabajadores clínicos (por ejemplo, enfermeras, médicos, trabajadores sociales) puedan ajustar y revisar las listas de pacientes para escenarios que abarcan desde rondas y reuniones de equipos interdisciplinarios hasta monitoreo general de pacientes.   

La aplicación tiene dos modos: 

- El modo conectado de EMR que se conecta a EMRs a través de FHIR. La aplicación modo conectado de EMR permanece en la vista previa privada y los clientes interesados o los administradores pueden solicitar acceso a la aplicación colocando Microsoft un correo electrónico en teamsforhealthcare@service.microsoft.com con información sobre su inquilino de Office 365. 
- El modo manual que permite a los equipos de atención médica agregar o aportar manualmente la información del paciente. La aplicación está disponible en la tienda de aplicaciones de Teams para que los usuarios finales la descarguen de forma predeterminada y se encuentre en la versión preliminar pública. La aplicación se puede restringir a determinadas secciones de usuarios que usan [directivas de configuración de aplicaciones en Microsoft Teams](../../teams-app-setup-policies.md)



## <a name="usage-example"></a>Ejemplo de uso

Durante las sesiones de redondeo de cada turno en el exterior, los clínicos se reúnen en la estación de enfermería para hablar de las últimas actualizaciones en el progreso con pacientes en el mismo día.  Resaltan las principales métricas fundamentales (no necesariamente médicas o que son explícitas en los registros médicos de los pacientes) y garantizan que el paciente está en la ruta de la alas derecha para descargar en función de su diagnóstico. Para redondear a estos pacientes, el enfermeros de enfermería configura la aplicación del paciente en un equipo en el que se agregan todos los médicos y agrega pacientes a la lista de pacientes. Durante los retrasos, las enfermeras y otros brindadores de cuidados para el acceso del paciente a Microsoft Teams y a la aplicación de pacientes en sus dispositivos móviles y actualizan la información relevante del paciente en su dispositivo y, a continuación, cualquier persona en el equipo de cuidados puede ver dichas actualizaciones y notas Mantente sincronizado. Dos veces por día, al principio y al final de un turno, también tienen reuniones de equipo de displicinary para repasar la lista de pacientes y usar la aplicación de pacientes para protegerse y compartir información sobre cada paciente con la aplicación de pacientes en una pantalla grande. A menudo, determinados médicos también pueden llamar a estas reuniones de Teams de forma remota y seguir siendo parte de la discusión. 

## <a name="configure-patients-app"></a>Configurar la aplicación para pacientes

Para obtener información sobre cómo preparar su entorno para usar la aplicación para pacientes de modo EMR, consulte [integración de registros de asistencia médica electrónica en Microsoft Teams](patients-app.md). También tendrá que ver [las directivas de configuración de administración de aplicaciones en Microsoft Teams](../../teams-app-setup-policies.md) para habilitar la aplicación para pacientes para su organización.

<!-- For information on how your end users can access and install the Patients App to a team that they own or manage, you will need to see [End user documentation for the Patients App]() -->

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="related-topics"></a>Temas relacionados

[Integración de registros sanitarios electrónicos en Microsoft Teams](patients-app.md)
