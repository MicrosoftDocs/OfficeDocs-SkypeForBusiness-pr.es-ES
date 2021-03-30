---
title: Aprovisionamiento remoto e inicio de sesión para dispositivos Android de Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: prgholve
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo aprovisionar e iniciar sesión de forma remota en dispositivos Android de Teams
ms.openlocfilehash: 43a025c0cc68fb7f10015d69298f8dd75f9003e8
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410384"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a>Aprovisionamiento remoto e inicio de sesión para dispositivos Android de Teams

Los administradores de TI pueden aprovisionar e iniciar sesión de forma remota en un dispositivo Android de Teams. Para aprovisionar un dispositivo de forma remota, el administrador debe cargar los IDs mac de los dispositivos que se aprovisionan y crear un código de verificación. Todo el proceso se puede completar de forma remota desde el Centro de administración de Teams.

## <a name="review-the-supported-devices"></a>Revisar los dispositivos compatibles

En la lista siguiente se muestran los requisitos de firmware del dispositivo Android.

|Categoría de dispositivo|Modelo de dispositivo|Versión de firmware|
|-|-|-|
|Teléfonos de Teams|Yealink T55/T56/T58|58.15.0.124|
|Teléfonos de Teams|Yealink VP59|91.15.0.58|
|Teléfonos de Teams|Yealink CP960|73.15.0.117|
|Teléfonos de Teams|Yealink MP56/MP54/MP58|122.15.0.36|
|Teléfonos de Teams|Crestron UC-2|1.0.3.52|

## <a name="add-a-device-mac-address"></a>Agregar una dirección MAC del dispositivo

Complete los pasos siguientes para aprovisionar un nuevo dispositivo.

1. Inicie la sesión en el Centro de administración de Teams
2. Expandir **dispositivos**.
3. Seleccione **Aprovisionar nuevo dispositivo** en la **pestaña** Acciones.

En la **ventana Aprovisionar nuevos dispositivos,** puede agregar la dirección MAC manualmente o cargar un archivo.

### <a name="manually-add-a-device-mac-address"></a>Agregar manualmente una dirección MAC del dispositivo

1. En la **pestaña Activación en** espera, seleccione Agregar **id. de MAC.**

   ![Agregar manualmente una dirección mac del dispositivo](../media/remote-provision-6.png)

1. Escriba el id. de MAC.
1. Escriba una ubicación que ayude a los técnicos a identificar dónde instalar los dispositivos.
1. Seleccione **Aplicar** cuando haya terminado.

### <a name="upload-a-file-to-add-a-device-mac-address"></a>Cargar un archivo para agregar una dirección MAC del dispositivo

1. En la **pestaña Activación en** espera, seleccione Cargar los **IDs mac.**
2. Descargue la plantilla de archivo.
3. Escriba el id. y la ubicación de MAC y, después, guarde el archivo.
4. **Seleccione archivo** y, a continuación, **seleccione Cargar**.

## <a name="generate-a-verification-code"></a>Generar un código de verificación

Necesita un código de verificación para los dispositivos. El código de verificación se genera en masa o en el nivel del dispositivo y es válido durante 24 horas.

1. En la **pestaña Activación en** espera, seleccione un id. de MAC existente.
   Se crea una contraseña para la dirección MAC y se muestra en la **columna Código de** verificación.

2. Proporcione la lista de los IDs MAC y los códigos de verificación a los técnicos de campo. Puede exportar los detalles directamente en un archivo y compartir el archivo con el técnico que está realizando el trabajo de instalación real.

## <a name="provision-the-device"></a>Aprovisionar el dispositivo

Cuando el dispositivo está encendido y conectado a la red, el técnico aprovisiona el dispositivo. Estos pasos se completan en el dispositivo de Teams.

1. El técnico selecciona **Aprovisionar dispositivo** en **configuración.**  

   ![Opción Aprovisionar nuevo dispositivo desde la pestaña Acciones](../media/provision-device1.png)
  
2. El técnico escribe el código de verificación específico del dispositivo en el campo de entrada proporcionado.

   ![Aprovisionar verificación de nuevo dispositivo](../media/provision-device-verification1.png)

   Una vez que el dispositivo se aprovisiona correctamente, el nombre del inquilino aparece en la página de inicio de sesión.

   ![Nombre del inquilino en la página de inicio de sesión](../media/provision-code.png)

## <a name="sign-in-remotely"></a>Iniciar sesión de forma remota

El dispositivo aprovisionado aparece en la **pestaña Esperando inicio de sesión.** Inicie el proceso de inicio de sesión remoto seleccionando el dispositivo individual.

1. Seleccione un dispositivo en la **pestaña Esperando inicio de sesión.**

   ![La ventana con una lista de dispositivos listos para iniciar sesión.](../media/remote-device1.png)

2. Siga las instrucciones de **Iniciar sesión en un usuario** y, a continuación, seleccione **Cerrar**.

   ![la ventana Iniciar sesión en un usuario para un dispositivo individual](../media/sign-in-user.png)

## <a name="related-article"></a>Artículo relacionado

- [Administrar los dispositivos en Teams](device-management.md)
- [Actualizar dispositivos de Teams de forma remota](remote-update.md)
