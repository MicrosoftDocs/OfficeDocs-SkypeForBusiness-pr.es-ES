---
title: Inscripción de usuarios para la autenticación de tarjetas inteligentes
TOCTitle: Inscripción de usuarios para la autenticación de tarjetas inteligentes
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn308570(v=OCS.15)
ms:contentKeyID: 56271349
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Inscripción de usuarios para la autenticación de tarjetas inteligentes

 

_**Última modificación del tema:** 2016-12-08_

En general, existen dos métodos para inscribir a los usuarios en la autenticación de tarjeta inteligente. El método más sencillo consiste en que los usuarios se inscriban directamente en la autenticación de tarjeta inteligente a través de la inscripción web; el más complejo consiste en usar un Enrollment Agent. Este tema se centra en la autoinscripción para usar certificados de tarjeta inteligente.

Para más información sobre la inscripción en nombre de usuarios como Enrollment Agent, consulte Realizar inscripciones de certificados en nombre de otros usuarios, en [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).

## Para inscribir a usuarios en la autenticación de tarjeta inteligente

1.  Inicie sesión en la estación de trabajo de Windows 8 con las credenciales de un usuario habilitado para Lync.

2.  Inicie Internet Explorer.

3.  Vaya a la página **Inscripción web de entidad de certificación** (p. ej., https://MiCA.contoso.com/certsrv).
    

    > [!NOTE]
    > Si usa Internet Explorer&nbsp;10, puede que tenga que ver este sitio web en modo de compatibilidad.



4.  En la **página principal**, elija **Solicitar un certificado**.

5.  Luego elija **Solicitud avanzada**.

6.  Elija **Crear y enviar una solicitud a esta CA**.

7.  Seleccione **Usuario de tarjeta inteligente** en la sección **Plantilla de certificado** y complete la solicitud de certificado avanzada con los siguientes valores:
    
      - En **Opciones de clave**, confirme la siguiente configuración:
        
          - Active el botón de radio **Crear conjunto de claves nuevo**
        
          - En **CSP**, seleccione **Proveedor base de cifrado para tarjetas inteligentes de Microsoft**
        
          - En **Uso de la clave**, seleccione **Exchange** (es la única opción disponible).
        
          - En **Tamaño de la clave**, escriba **2048**
        
          - Confirme que está activado **Nombre automático de contenedor de claves**
        
          - Deje las demás casillas desactivadas.
    
      - En **Opciones adicionales**, confirme los siguientes valores:
        
          - En **Formato de la solicitud**, seleccione **CMC**.
        
          - En **Algoritmo hash**, seleccione **sha1**.
        
          - En **Nombre descriptivo**, escriba **Certificado de tarjeta inteligente**.

8.  Si utiliza un lector de tarjetas inteligentes físico, inserte la tarjeta inteligente en el dispositivo.

9.  Haga clic en **Enviar** para enviar la solicitud de certificado.

10. Cuando se le pida, escriba el PIN que se usó para crear la tarjeta inteligente virtual.
    

    > [!NOTE]
    > El valor del PIN de tarjeta inteligente virtual predeterminado es “12345678”.



11. Una vez emitido el certificado, haga clic en **Instalar este certificado** para completar el proceso de inscripción.
    

    > [!NOTE]
    > Si la solicitud de certificado presenta el error “Este explorador web no es compatible con la creación de solicitudes de certificados”, hay tres formas de resolver el problema: 
    > <OL>
    > <LI>
    > <P>Habilitar la Vista de compatibilidad en Internet Explorer</P>
    > <LI>
    > <P>Habilitar la opción Activar configuración de Intranet en Internet Explorer</P>
    > <LI>
    > <P>Activar la opción Restablecer todas las zonas al nivel predeterminado en la pestaña Seguridad del menú de opciones de Internet Explorer.</P></LI></OL>


