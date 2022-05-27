---
title: Auditoría multiinquilino
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Registro de auditoría para TRM.
f1keywords: ''
ms.openlocfilehash: 3681f50f0e15a7688a944c14e69907ba53dd2817
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676621"
---
# <a name="audit-logging-in-the-teams-rooms-managed-service"></a>Registro de auditoría en el servicio administrado de Salas de Teams

La auditoría en Salas de Teams servicio Administrado (TRM) le permite buscar registros de auditoría para las actividades realizadas en el portal por usuarios y administradores. Esta característica está habilitada de forma predeterminada. Solo el administrador de servicios administrados tiene permiso para exportar y, a continuación, ver los registros.

> [!NOTE]
> Las acciones realizadas en el servicio TRM no se registran en Microsoft 365 ni en la auditoría de Office 365 

## <a name="exporting-logs"></a>Exportar registros

Al exportar todos los resultados de una búsqueda de registros de auditoría, los datos sin procesar del registro de auditoría unificado se copian en un archivo csv (valores separados por comas) que se descarga en el equipo local. 

**Para descargar registros** 

1. Vaya a **Configuración > registros de auditoría generales de >**.
1. Para definir el intervalo de fechas de los registros de interés, escriba la **Fecha de inicio** y la **Fecha de finalización.**

   > [!NOTE]
   > Los registros solo están disponibles durante un máximo de 180 días.

1. Seleccione **Descargar registros.**

   ![Intervalo de fechas del registro de auditoría](../media/multi-tenant-auditing.png)

   Un mensaje que se muestra en la parte inferior de la ventana le pide que abra o guarde el archivo CSV. 

1. Seleccione **Guardar** > **como** y guarde el archivo CSV en el equipo local. 

1. Se tarda un tiempo en descargar muchos resultados de búsqueda al buscar todas las actividades o en un intervalo de fechas amplio. Cuando el archivo CSV termine de descargarse, se mostrará un mensaje en la parte inferior de la ventana.

## <a name="detailed-properties-in-the-audit-log"></a>Propiedades detalladas en el registro de auditoría

En la tabla siguiente se describen las propiedades que se incluyen en el CSV.

|Propiedad|Descripción|
| - | - |
|activity.category|<p>La categoría del objeto en el que se realizó la acción. Valores posibles:</p><p>**Usuario, asignación, partnerinvitation, rol**</p>|
|activity.objectName|El nombre del objeto modificado.|
|activity.operation|El tipo de operación realizada. Los valores posibles son: **Crear, Actualizar, Eliminar** |
|activity.resultStatus|<p>Indica si la acción (especificada en la propiedad **activity.operation** ) se realizó correctamente o no.</p><p>El valor es **Correcto** o **Fallido**.</p>|
|activity.tenantId|El GUID del inquilino en el que se realizó la acción|
|creationTime|La fecha y la hora en hora universal coordinada (UTC) en formato ISO cuando el usuario realizó la actividad.|
|user.userId|El usuario que realizó la acción que provocó que se registrara el registro.|
|user.userTenantId|El GUID del inquilino para el usuario que realizó la acción|


