---
title: "Conf. d’une autorité de cert. d’entreprise pour l’auth. par carte à puce"
TOCTitle: "Conf. d’une autorité de cert. d’entreprise pour l’auth. par carte à puce"
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn308571(v=OCS.15)
ms:contentKeyID: 56271353
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de CA empresarial para la autenticación de tarjetas inteligentes

 

_**Última modificación del tema:** 2016-12-08_

En la siguiente sección, se describe cómo configurar una entidad de certificación (CA) raíz empresarial para admitir la autenticación de tarjeta inteligente. Si quiere información sobre cómo instalar una CA raíz empresarial, consulte Instalar una entidad emisora de certificados raíz de empresa, en [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364).

## Configuración de una entidad de certificación raíz empresarial para admitir la autenticación de tarjeta inteligente

En los siguientes pasos, se describe cómo configurar una CA raíz empresarial para admitir la autenticación de tarjeta inteligente:

1.  Inicie sesión en el equipo de la CA empresarial usando una cuenta de administrador de dominio.

2.  Inicie el Administrador del sistema y compruebe que está instalado el rol Inscripción web de entidad de certificación.

3.  En el menú **Herramientas administrativas**, abra la consola de administración de **Entidad de certificación**.

4.  En el panel de navegación, expanda **Entidad de certificación**.

5.  Haga clic con el botón secundario en **Plantillas de certificado**, elija **Nueva** y, luego, elija **Plantilla de certificado que se va a emitir**.

6.  Elija **Enrollment Agent**, **Usuario de tarjeta inteligente** e **Inicio de sesión de Tarjeta inteligente**.

7.  Haga clic en **Aceptar**.

8.  Haga clic con el botón secundario en **Plantillas de certificado**.

9.  Elija **Administrar**.

10. Abra las propiedades de la plantilla Usuario de tarjeta inteligente.

11. Haga clic en la pestaña **Seguridad**.

12. Cambie los permisos como se indica a continuación:
    
      - Agregue cuentas de usuario individuales de AD con los permisos Leer/Inscribir (permitir), o
    
      - Agregue un grupo de seguridad que contenga los usuarios de tarjeta inteligente con permisos Leer/Inscribir (permitir), o
    
      - Agregue el grupo Usuarios del dominio con los permisos Leer/Inscribir (permitir)

