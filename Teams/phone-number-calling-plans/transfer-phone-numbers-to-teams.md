---
title: Transferir números de teléfono a Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: ''
ms.openlocfilehash: 53c17cdd3a1b6726e0219147e4dadd1cba7b25ff
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827938"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>Transferir números de teléfono a Microsoft Teams

Use el Asistente de migración en el centro de administración de Microsoft Teams para transferir los números de teléfono de su proveedor de servicios actual a teams. Después de trasladar los números de teléfono a Teams, Microsoft se convertirá en su proveedor de servicios y le facturará los números de teléfono.

Antes de empezar, le recomendamos que revise la información de la [solicitud de portabilidad](port-order-overview.md). Si tiene números de servicio para puentes de conferencias de acceso telefónico local, operadores automáticos u otros números de servicio, números de teléfono gratuitos o más de 999 números de teléfono de usuario (suscriptor) que necesita transferir a Teams, vea [administrar números de teléfono de su organización](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para descargar los formularios correctos y enviarlos.

  > [!NOTE]
  > Procesamos los pedidos de los puertos para la transferencia de números de teléfono solo en días hábiles de Estados Unidos y no en días festivos ni fines de semana.

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>Crear una solicitud de portabilidad y transferir los números de teléfono a teams

> [!NOTE]
> Si su país o región no aparecen en la lista del Asistente para la migración en el centro de administración de Microsoft Teams, puede [enviar manualmente una solicitud de portabilidad](manually-submit-port-order.md).

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**números de teléfono**de **voz** > . Haga clic en **números**y, a continuación, haga clic en **Puerto** para iniciar el Asistente para la migración.
2. Revise la información de la **Página INTRODUCCIÓN** y, después, cuando esté listo, haga clic en **siguiente**.
3. En la página **seleccionar la ubicación y el tipo de número** , especifique lo siguiente y, a continuación, haga clic en **siguiente**:

    - **País o región**: país o región donde estás recibiendo números.
    - **Tipo de número de teléfono**: tipo de número, como números geográficos o gratuitos.
    - **Números asignados a**: a qué se asignan los números. Por ejemplo, usuarios o características de voz o conferencias.

4. En la página **Agregar información de cuenta** , complete los pasos siguientes y, a continuación, haga clic en **siguiente**.

    > [!IMPORTANT]
    > La información que se muestra en esta página está determinada por el país o la región y el tipo de número. Cada país y región tienen diferentes reglamentos en la información que se necesita para el número de puertos. Es posible que la información que aparece en esta página sea distinta de la que se describe aquí.

    - **Detalles del pedido**: 
        - **Nombre del pedido**: nombre de su pedido
        - **Correos electrónicos de notificación**: direcciones de correo electrónico para recibir notificaciones de pedidos. Si escribe varias direcciones de correo electrónico, sepárelos con un punto y coma.
        - **Fecha**de transferencia: fecha de transferencia emitida por tu proveedor de servicios actual.
    - **Detalles del número de teléfono**
        - **Tipo de Puerto**: ya sea que estés haciendo un puerto completo para transferir todos tus números o un puerto parcial para transferir algunos de tus números.
    - **Persona que solicita detalles**  
        - El nombre de la organización y los detalles de contacto de la persona que solicita la transferencia.
    - **Detalles del proveedor actual**
        - **Número de teléfono de facturación (BTN)**: tu BTN en formato E. 164, que requiere un signo + para anteponer el número. Por ejemplo, para un número de Norteamérica, use el formato + 1XXXYYYZZZZ.
        - Otros detalles, como el nombre de su proveedor de servicios actual, su número de cuenta y su dirección de servicio.
            
5. En la página **agregar números** , haga clic en **seleccionar un archivo**, busque y seleccione el archivo CSV que contiene los números de teléfono que desea transferir y, a continuación, haga clic en **siguiente**.  

    > [!NOTE]
    > El archivo CSV debe tener solo una columna con un encabezado denominado PhoneNumber. Cada número de teléfono debe estar en una fila separada y solo puede contener dígitos o en formato E. 164.

6. En la página **completar su pedido** , haga clic en **cargar una carta firmada de autorización** para cargar una copia analizada de la carta de autorización firmada (Loa).

    Si aún no ha descargado ni firmado la LOA, haga lo siguiente:
    
    1. Haga clic en **descargar la plantilla** para descargar la loa de su país o región. 
    2. Imprima la LOA.
    3. Tenga la firma de la otra persona autorizada para realizar cambios en la cuenta.
    4. Digitalice la LOA con firma y, a continuación, haga clic en **cargar una carta firmada de autorización** para cargarla.

    > [!NOTE]
    > Después de cargar la LOA, envíe su pedido. Solo cargar la LOA no es suficiente. También tienes que enviar el pedido para que se procese.

7. Revise los detalles de su pedido y, a continuación, haga clic en **Enviar**.


## <a name="what-happens-next"></a>¿Qué sucede ahora?

Cuando recibamos tu solicitud de portabilidad, recibirás un mensaje de correo electrónico para verificar tu solicitud. Tu solicitud se ha verificado y actualizado diariamente y se te notificará su progreso y estado en el correo electrónico. Si su solicitud es rechazada, se le pedirá que abra un vale de soporte técnico.

Para ver el estado de la solicitud de portabilidad, en el navegación izquierdo del centro de administración de Microsoft Teams, vaya a >**pedidos**de **voz** > y, a continuación, haga clic en **historial de pedidos**. Cada estado de pedido de puerto se muestra en la columna **Estado** . Para obtener más información, consulte [¿cuál es el estado de sus solicitudes de portabilidad?](port-order-status.md).

## <a name="related-topics"></a>Temas relacionados

- [¿Qué es un pedido de portabilidad?](port-order-overview.md)
- [Diferentes tipos de números de teléfono que se usan para Planes de llamada](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Administrar los números de teléfono para su organización](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Términos y condiciones de las llamadas de emergencia](../emergency-calling-terms-and-conditions.md)
- [Etiqueta de renuncia para llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)