---
title: Configurar teléfonos de área común
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Obtenga información sobre los pasos de implementación para obtener el firmware correcto, actualizarlo si es necesario, asignar licencias y configurar las opciones de teléfonos de área común.
ms.openlocfilehash: bcf7d8eaf287af0b801168c62e7c22915f735aa2
ms.sourcegitcommit: 6b868f683e1f2354eb42fdf33911e77b7a3a83e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2018
---
# <a name="set-up-common-area-phones"></a>Configurar teléfonos de área común
Normalmente, se coloca un teléfono de área común (CAP) en un área como una sala de espera o a otra área que está disponible para una gran cantidad de personas. Por ejemplo, un teléfono de área de recepción de teléfono puerta teléfono o salas de reuniones, las mayúsculas se configuran como dispositivos en lugar de los usuarios e iniciar sesión automáticamente en una red. En los pasos siguientes, le ayudaremos a configurar para el sistema telefónico con planes de llamar a una cuenta, por lo que puede implementar estos tipos de teléfonos para su organización.

## <a name="prerequisites-for-common-area-phones"></a>Requisitos previos para teléfonos de área común

Lo primero que debe hacer es confirmar que tiene lo siguiente:

 - Licencia de teléfono de área común de compra y un Plan de llamada.
 - Buscar y comprar teléfonos aprobados (ver la lista [aquí](deploying-skype-for-business-online-phones.md)).         
 - Actualice el firmware en los teléfonos (vea admitido firmware [en este tema](getting-phones-for-skype-for-business-online.md).  Puede comprobar el firmware de teléfono haciendo lo siguiente:       
    - **Los teléfonos Polycom VVX**: Ir a la **configuración de** > **estado** > **plataforma** > **aplicación** > **principal**.
    - **Teléfonos Yealink**: vaya al **estado** de la pantalla del teléfono principal.
    - **Teléfonos AudioCodes**: vaya al **menú** > **Estado del dispositivo** > **versión de Firmware** desde la pantalla de inicio. 
    - **Teléfonos de Lync Phone Edition (LPE)**: vaya al **menú** > **Información del sistema** desde la pantalla de inicio.

    Actualizaciones de firmware se administran mediante el Skype para servicio empresarial. Cada Skype para la empresa certificada firmware del teléfono se cargó en la Skype para servidor de actualización de negocio, y actualización de dispositivos está habilitado en todos los teléfonos de forma predeterminada. 

    Según el tiempo de inactividad en el teléfono y los intervalos de sondeo, teléfonos automáticamente descargar e instalar las compilaciones certificadas más recientes. Puede deshabilitar la configuración de actualización de dispositivo mediante el cmdlet [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) y establecer el parámetro *EnableDeviceUpdate* en `false`.

## <a name="setting-up-a-common-area-phone"></a>Configuración de un teléfono de área común
Debe seguir estos pasos:

### <a name="set-up-your-user-account-for-the-phone"></a>Configurar una cuenta de usuario para el teléfono

#### <a name="step-1---buy-the-licenses"></a>Paso 1: comprar las licencias
1. En el centro de administración de Office 365, vaya a **facturación** > **Servicios de compra**, y agregar **otros planes**.

    ![CAP license.png](../../images/cap-license.png)
2. Haga clic en **Teléfono de área común** > **comprar ahora** > en la página de **finalización de compra** haga clic en **comprar ahora**.
3. Haga clic en expandir **las suscripciones del complemento** y, a continuación, haga clic en para adquirir un Plan de llamar a. Elija la **nacionales llamar al Plan** o la **planeación de la llamada nacional e internacional**.

> [!Note]
> No necesita una licencia de sistema telefónico. Ha incluido con la licencia de **Teléfono de área común** .

Para obtener más información sobre las licencias, vea [Skype para profesionales y los equipos de Microsoft complemento licencias](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

#### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Paso 2: crear una nueva cuenta de usuario para el teléfono y asignar las licencias
1. En el centro de administración de Office 365, vaya a **los usuarios** > **Usuarios activos** > **Agregar un usuario**.
2. Colocar en un **nombre de usuario** , como "Main" para el nombre y el "Recepción" para el segundo nombre.
3. Colocar en un **nombre para mostrar** si no es así generar automáticamente como "Recepción principal".
4. Colocar en un **nombre de usuario** , como "MainReception" o "Mainlobby".
5. Para teléfonos de área común, es posible que desee establecer una contraseña manualmente o tener la misma contraseña para todos los teléfonos de área común. Además, es posible que piense anula la selección de **realizar este usuario cambiar su contraseña cuando inician sesión por primera vez en**.

    > [!Tip]
    > ¡ESPERAR! No haga clic en **Agregar**. Ugh, si hizo clic en **Agregar** el hacer esto: Centro de administración de Office 365 > **usuarios** > **usuarios activos** y, a continuación, busque el usuario. A continuación, en la página de propiedades del usuario, haga clic en **licencias de producto** y, a continuación, haga clic en **Editar**. En la página **licencias de producto** , encienda el **Teléfono de área común** y de selección ya sea un **Nacionales llamar a planear** o un nacionales y **Llamar a planear internacional**.

6. Si son aún no existe, asigne las licencias para este usuario. En la misma página, haga clic para expandir **las licencias de producto**. Para activar el siguiente:
    - Teléfono de área común
    - A continuación, tendrá que escoger ya sea un **Llamar a planear nacionales** o un nacionales y **Llamar a planear internacional**.
     
    Asignación de las licencias tendrá el siguiente aspecto:

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > Como ya debe saber, Skype para empresarial Plan 2 se incluye con la licencia de **Teléfono de área común** .

Para obtener más detalles, vea [Agregar un usuario](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

#### <a name="step-3---assign-a-phone-number-to-the-user"></a>Paso 3: asignar a un número de teléfono al usuario
![logotipo-sfb-30x30.png](../../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**
1. En el centro de administración de Office 365 > **centros de administración** > **Skype para la empresa**.
2. En el **Skype para el centro de administración de negocio** >  **voz** > **los números de teléfono**.
3. Seleccione un número de la lista de números de teléfono y haga clic en **asignar**.
4. En la página **asignar** , en el cuadro de **usuario de voz** , escriba el nombre del usuario que se usa para el teléfono, a continuación, seleccione el usuario en, **Seleccione un usuario de voz de** lista desplegable. 
5. Mientras esté allí necesita agregar una dirección de emergencia. Una vez que buscar, mire en la **Seleccione emergencia dirección** para elegir el adecuado para usted.
6. Haga clic en **Guardar** y el usuario debe tener este aspecto:

    ![CAP-usuario-number.png](../../images/cap-user-number.png)

   > [!Note]
   > Los usuarios sólo aparecerá si tienen una licencia de **Sistema telefónico** aplicada. Si ya ha realizado esta, a continuación, en ocasiones, se tarda un poco para que el usuario aparezca en la lista.

Para obtener más cosas, vea [Introducción de los números de teléfono para los usuarios](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).

Si se lo está preguntando, también puede tomarse su número de teléfono que tiene con otro operador y "*puerto*" o transferirlos a través de Office 365. Vea, [transferir los números de teléfono para Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).

## <a name="step-4---setting-up-your-phone"></a>Paso 4: configurar el teléfono

**Establecer el modo en un teléfono**

El teléfono o teléfonos que tiene deben tener activado el modo de teléfono de área común. Es posible que desee comprobar para asegurarse de que lo hacen. 

**Este es un ejemplo de cómo configurar un teléfono Polycom VVX**

- Habilitar el modo de teléfono de área común para el VVX Polycom siguiendo estos pasos:
    1. En el explorador, conéctese a la interfaz web para que se puede habilitar el modo de capital.
    2. A continuación, vaya a **configuración** y en la opción de **Skype para configuración de negocio** , seleccione **Teléfono de área común**.
    3. Haga clic en **Sí** para guardar la configuración.

- Ahora que está habilitado el modo de capital, configurar el teléfono mediante la pantalla del teléfono. La presentación debe mostrar **CaAP está habilitado**. A continuación, haga lo siguiente:

    1. Haga clic en **configuración**.
    2. Seleccione **avanzada**.
    3. Escriba la contraseña.
    4. En **la configuración de administración**, seleccione **Configuración de teléfono de área común**.
    5. Habilitar el **modo de administración de CAP**y **CAP** .
    6. Haga clic en **Guardar configuración**.

- Ahora bien, el teléfono está listo para poder iniciar sesión en la pantalla principal.

    1. Iniciar sesión mediante la selección de **configuración** > **características** > **Skype para la empresa.**
    2. Seleccione **Las credenciales de usuario**y seleccione **Inicio de sesión de web (CAP)** para generar un código.
    3. Vaya al [portal de aprovisionamiento](http://aka.ms/skypecap)e iniciar sesión como **Administrador**.
    4. Escriba el nombre para mostrar (por ejemplo, Main recepción).

       > [!Note]
       > Si está activada la opción **Buscar sólo los teléfonos de área común** , desactive la casilla de verificación y busque de nuevo.'

    5. En la ventana de código de emparejamiento, escriba el código que aparece en el teléfono y haga clic en **aprovisionar**.

        Después de este último paso, el teléfono debe iniciar sesión automáticamente.

### <a name="related-topics"></a>See also

- Obtener más información acerca de los teléfonos disponibles en la [Implementación de Skype para teléfonos empresarial en línea](deploying-skype-for-business-online-phones.md).
- [Obtener teléfonos con Skype Empresarial Online](getting-phones-for-skype-for-business-online.md)


