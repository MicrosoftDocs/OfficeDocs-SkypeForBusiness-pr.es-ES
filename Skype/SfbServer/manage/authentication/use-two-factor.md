---
title: Use la autenticación en dos fases Skype Empresarial cliente y Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 'Resumen: use la autenticación en dos fases con Skype Empresarial Server y Skype Empresarial.'
ms.openlocfilehash: 3bcba5d4bdd6aacee794b40273b2cb92c83df50a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767868"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Use la autenticación en dos fases Skype Empresarial cliente y Skype Empresarial Server
 
**Resumen:** Use la autenticación en dos fases Skype Empresarial Server y Skype Empresarial.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Inicie sesión en Skype Empresarial inicio de sesión por primera vez

La información de inicio de sesión normalmente se configura automáticamente cuando Skype Empresarial se instala. Pero la primera vez que use Skype Empresarial, es posible que tenga que iniciar manualmente el cliente.
  
### <a name="to-sign-in-for-the-first-time"></a>Para iniciar sesión por primera vez

1. Inicie sesión en la red de su organización.
    
2. Seleccione **Iniciar**  >  **todos los programas**  >  **Skype Empresarial**.
    
    Debería ver la pantalla de inicio de sesión.
    
    - Si el cuadro de dirección de inicio de sesión ya está rellenado, confirme que la dirección mostrada es correcta.
    
    - Si no es correcto, o si el cuadro está vacío, escriba la dirección de inicio de sesión (normalmente es la misma que la dirección de correo electrónico).
    
    - Si se muestra un cuadro de contraseña vacío, agregue la contraseña.
    
3. Seleccione **Iniciar sesión**.
    
## <a name="sign-out-of-skype-for-business"></a>Cerrar sesión de Skype Empresarial

Cuando haya terminado de usar Skype Empresarial, puede cerrar la pantalla, cerrar sesión o salir del programa, todo desde el menú Archivo. En la tabla siguiente se explican las diferencias en las opciones.
  
|**Opción**|**Lo que hace**|**Cómo realizarlo**|
|:-----|:-----|:-----|
|Cerrar  <br/> |Cierra la pantalla, pero permite que Skype Empresarial sesión identificada con el identificador de usuario continúe en ejecución. Esto es para que pueda seguir recibiendo notificaciones e interactuar con otros usuarios. <br/> <br/> Puedes recuperar la pantalla en cualquier momento haciendo clic en el icono Skype Empresarial en la barra de tareas o en el área de notificación en la parte inferior de la pantalla.  <br/> | En la Skype Empresarial principal, realice una de las siguientes acciones: <br/> 1. Seleccione el **botón Opciones** y, a continuación, **seleccione Cerrar**  >  **archivo**.  <br/> 2. Haga clic en **el botón** Cerrar (X) en la esquina superior derecha de la ventana. <br/> |
|Cerrar sesión  <br/> |Finaliza la sesión asociada con el identificador de usuario, pero Skype Empresarial se sigue ejecutando en segundo plano. Al cerrar sesión, aparecerá la ventana de inicio de sesión.  <br/> **Sugerencia:** Seleccione **Eliminar mi información de inicio de** sesión cuando cierre la sesión para quitar el registro del identificador de inicio de sesión y la contraseña del equipo. Al hacerlo, es posible que sea más fácil para los usuarios de soporte técnico solucionar problemas de inicio de sesión. También puede ayudar a garantizar que la información de inicio de sesión sea más segura al dificultar que los usuarios no autorizados inicien sesión con sus credenciales. <br/> |En la Skype Empresarial principal, seleccione el botón **Opciones** y, a continuación, seleccione **Cerrar**  >  **sesión del archivo.**  <br/> |
|Salir  <br/> |Finaliza la sesión Skype Empresarial y cierra Skype Empresarial en el equipo. Después de salir, si desea reiniciar, seleccione **Iniciar**  >  **todos los programas > Skype Empresarial.** <br/> |En la Skype Empresarial principal, seleccione el botón **Opciones** y, a continuación, seleccione **Salida**  >  **de archivo**.  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Inicie sesión en Skype Empresarial con una tarjeta inteligente

Algunas organizaciones ahora usan un proceso de inicio de sesión de varios pasos, denominado autenticación en dos fases, para aumentar la seguridad de sus usuarios. Si se espera que use esta opción, necesitará una "tarjeta inteligente" para iniciar sesión en Skype Empresarial. Las tarjetas inteligentes pueden ser físicas o virtuales:
  
- **Físico** Acerca del tamaño de una tarjeta de crédito. Se inserta en un lector de tarjetas inteligentes al iniciar sesión.
    
- **Virtual** No es un objeto físico, sino un identificador electrónico que se escribe en un chip especial del equipo, que básicamente crea la tarjeta inteligente en el equipo. Solo está disponible para su uso Windows 8 equipos que contienen el chip TPM (Módulo de plataforma de confianza).
    
### <a name="enroll-your-smart-card"></a>Inscribir la tarjeta inteligente

Para poder iniciar sesión con una tarjeta inteligente, la tarjeta debe estar "registrada", es decir, las credenciales de usuario deben identificarse con la tarjeta. Este es el caso de si la tarjeta es física o virtual. Este proceso ya lo puede llevar a cabo su Skype Empresarial Server administrador. Compruebe con ellos si no está seguro de si se ha hecho.
  
> [!NOTE]
> Dado que cada tarjeta inteligente virtual está asociada solo con el dispositivo en el que está instalada, deberá inscribirse una tarjeta independiente para cada Windows 8 equipo que use. 
  
### <a name="to-manually-enroll-your-smart-card"></a>Para inscribir manualmente la tarjeta inteligente

1. Inicie sesión en el equipo en el que va a ejecutar Skype Empresarial.
    
2. Con Internet Explorer, vaya a la página Inscripción web de entidad de certificación de su organización. 
    
    Solicite a Skype Empresarial Server administrador la dirección web de este recurso si aún no la tiene. La dirección URL tendrá un aspecto parecido a este: https://MyCA .[ yourcompanyname].com/certsrv.
    
    > [!NOTE]
    > Si estás usando Internet Explorer 10, es posible que necesites ver este sitio web en modo de compatibilidad. 
  
3. Cuando se le pida que inicie sesión en la página de certificación, inicie sesión con su cuenta de dominio (en lugar de como administrador del equipo).
    
4. En la página de bienvenida del sitio web, seleccione **Solicitar un certificado**.
    
5. Seleccione **Solicitud avanzada**.
    
6. Seleccione **Crear y enviar una solicitud a esta ENTIDAD de certificación** y, a continuación, haga clic **en Siguiente**.
    
7. Ahora verá una página denominada Estación de inscripción de tarjetas inteligentes. Apruebe la solicitud para instalar el control ActiveX y, a continuación, complete el formulario Solicitud de certificado avanzada de la siguiente manera:
    
    a. Seleccione **Usuario de tarjeta inteligente en** la lista desplegable Plantilla **de** certificado.
    
    b. Seleccione **Crear nuevo conjunto de claves**.
    
    c. Busque la información del fabricante en la etiqueta de la tarjeta inteligente y seleccione ese fabricante en la lista desplegable **CSP.**
    
    d. Seleccione **CSP** como formato de solicitud, si aún no está seleccionado.
    
    e. Seleccione **sha1** en la lista desplegable Algoritmo hash, si aún no está seleccionada.
    
    f. Asigne al certificado un nombre que reconocerá y haga clic en **Enviar**.
    
8. Ahora inserte la tarjeta inteligente en blanco en el lector de tarjetas adjunto a la estación de inscripción y haga clic **en Inscribir**.
    
9. Cuando se le pida, escriba su número de identificación personal (PIN) y, a continuación, haga clic en **Aceptar**.
    
    > [!NOTE]
    > Si la persona de soporte técnico no le ha dado un PIN especial que usar para inscribir la tarjeta inteligente, use el valor predeterminado de PIN de tarjeta inteligente, que es 12345678. 
  
10. Seleccione la opción para forzar al usuario (usted) a cambiar el PIN la primera vez que se usa la tarjeta inteligente.
    
11. Ahora inserte la tarjeta inteligente en blanco en el lector de tarjetas adjunto a la estación de inscripción y haga clic **en Inscribir**.
    
12. Cuando se le pida, escriba su número de identificación personal (PIN) y, a continuación, haga clic en **Aceptar**.
    
    > [!NOTE]
    > Si la persona de soporte técnico no le ha dado un PIN especial que usar para inscribir la tarjeta inteligente, use el valor predeterminado de PIN de tarjeta inteligente, que es 12345678. 
  
13. Seleccione la opción para forzar al usuario (usted) a cambiar el PIN la primera vez que se usa la tarjeta inteligente.
    
14. Haga **clic en** Aceptar para confirmar que el certificado mostrado tiene su información.
    
15. Una vez que vea el aviso de que el certificado se ha emitido, haga clic en **Instalar este certificado** para completar el proceso de inscripción.
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Inicie sesión en Skype Empresarial con sus credenciales de tarjeta inteligente

Antes de usar la tarjeta inteligente por primera vez,  se recomienda hacer clic en Eliminar mi información de inicio de sesión en la Skype Empresarial inicio de sesión. Al hacerlo, se borran las credenciales de inicio de sesión almacenadas en el equipo y se elimina un posible origen de error.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Para iniciar sesión en Skype Empresarial con las credenciales de la tarjeta inteligente

1. Inicie el Skype Empresarial cliente.
    
2. En la pantalla Iniciar sesión, escriba el  nombre de la cuenta de usuario de inicio de sesión en el cuadro Dirección de inicio de sesión y, a continuación, haga clic **en Iniciar sesión**.
    
3. Si usa una tarjeta inteligente virtual, omita este paso.
    
    Si usa una tarjeta inteligente física, inserte la tarjeta inteligente en el lector de tarjetas inteligentes y se le pedirá que lo haga y, a continuación, haga clic en **Aceptar** cuando se detecte la tarjeta.
    
4. Escriba el número de PIN que necesita para la tarjeta inteligente y, a continuación, haga clic en **Aceptar**.
    
    > [!NOTE]
    > Si la persona de soporte técnico no le asignó un número de PIN de tarjeta inteligente, use el valor predeterminado, que es 12345678. 
  
## <a name="see-also"></a>Consulte también

[Administrar la autenticación en dos fases en Skype Empresarial Server](two-factor-authentication.md)
  
[Configurar la autenticación en dos fases en Skype Empresarial Server](configure-two-factor.md)
