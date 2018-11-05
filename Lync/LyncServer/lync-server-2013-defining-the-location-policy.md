---
title: 'Lync Server 2013: Definir una directiva de ubicación'
TOCTitle: Definir una directiva de ubicación
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48276873
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definir una directiva de ubicación para Lync Server 2013

 

_**Última modificación del tema:** 2012-10-29_

Cada directiva de ubicación contiene la información siguiente:

  - **Servicios de emergencia habilitados**  
    Si se define en **Sí**, se habilita al cliente para E9-1-1. Cuando un cliente se registra, intentará adquirir una ubicación del Servicio de información de ubicaciones e incluirá la información de ubicación como parte de una llamada de emergencia.

<!-- end list -->

  - **Ubicación obligatoria**  
    Solo se usa cuando **Servicios de emergencia habilitados** está definido como **Sí**.
    
    Configure el parámetro de **Ubicación obligatoria** para definir el comportamiento del cliente. Si se define el valor en **No**, no se pedirá al usuario una ubicación. Si se define en **Sí**, se pedirá al usuario una ubicación, pero este puede anular la solicitud. Si se define en **Declinación de responsabilidades**, el usuario deberá especificar una ubicación y no podrá anular la solicitud hasta que haya introducido una solicitud. En ambos casos el usuario puede continuar usando el cliente.
    

    > [!NOTE]
    > El texto de declinación de responsabilidades no aparecerá si el usuario ha introducido manualmente una ubicación antes de ser habilitado para E9-1-1 y los usuarios que ya hayan visto la declinación de responsabilidades no recibirán las actualizaciones de dicho texto.



<!-- end list -->

  - **Declinación de responsabilidad de servicio de emergencia mejorado**  
    En esta configuración se especifica la declinación de responsabilidad que los usuarios ven si rechazan la solicitud de una ubicación. En Lync Server 2013, usa la directiva de ubicación para definir configuraciones regionales diferentes o diferentes conjuntos de usuarios.
    

    > [!NOTE]
    > Esta configuración de directiva de ubicación es diferente de Lync Server 2010, donde se usaba el cmdlet <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> para definir una declinación de responsabilidad global para toda la organización. Si ya existe una declinación de responsabilidad global, especifique la declinación de responsabilidad en la directiva de ubicación. Es decir, Lync Server 2013 usa solo declinaciones de responsabilidad especificadas en la directiva de ubicación.



<!-- end list -->

  - **Cadena de marcado de emergencia**  
    La cadena de marcado que indica que la llamada en cuestión es una llamada de emergencia. La **cadena de marcado de emergencia** comporta la adición a la llamada de información de ubicación y devolución de llamada por parte del cliente.
    

    > [!NOTE]
    > Si su organización no utiliza un prefijo de acceso de línea externo, no tendrá que crear una regla de normalización de planes de marcado correspondiente que añada un signo “+” a la cadena 911 antes de enviar la llamada al enrutamiento de salida en el servidor de grupo de Lync; el signo “+” se agregará automáticamente por parte del cliente de Lync como resultado de la directiva de ubicación. Sin embargo, si su sitio utiliza un prefijo de acceso externo, agregue una regla de normalización a la directiva de plan de marcado aplicable que quite el prefijo de acceso externo y agregue el signo “+”. Por ejemplo, si su ubicación utiliza un prefijo de acceso externo 9 y un usuario marca 9 911 para realizar una llamada de emergencia, el cliente utilizará su directiva de plan de marcado para normalizarlo a +911 antes de que las rutas en el perfil de ubicación del autor de la llamada lo evalúen.



<!-- end list -->

  - **Máscaras de cadena de marcado de emergencia**  
    Una lista de cadenas de marcado separadas por caracteres de punto y coma que deben convertirse a la **cadena de marcado de emergencia** especificada. Por ejemplo, es posible que desee agregar 112, que es el número del servicio de emergencia para la mayor parte de Europa. Un usuario de Lync visitante proveniente de Europa puede que no sepa que el 911 es el número de emergencia en los Estados Unidos, pero puede marcar el 112 y obtener el mismo resultado. Al igual que con la cadena de marcado de emergencia, no incluya un signo “+” antes de cada número y, si utiliza códigos de acceso de línea externa, asegúrese de que existen reglas de normalización en la directiva del plan de marcado de los usuarios para quitar el dígito del código de acceso.

<!-- end list -->

  - **Uso de RTC**  
    El nombre del uso de RTC que contiene las rutas de acceso que determinan en qué tronco SIP o puerta de enlace RTC se realizarán las llamadas de emergencia.
    

    > [!NOTE]
    > Solo se puede asignar un uso a una directiva de ubicación. Este uso de RTC reemplaza los usos de RTC asignados a la directiva de voz del usuario, pero solo se aplica a llamadas realizadas a la cadena de marcado de emergencia o a una de las máscaras de la cadena de marcado de emergencia.



<!-- end list -->

  - **URI de notificación**  
    Especifica los URI de SIP del personal de seguridad para que reciban una notificación por mensajería instantánea cuando se realice una llamada de emergencia. Se admiten los grupos de distribución.

<!-- end list -->

  - **URI de conferencia**  
    Especifica el número de llamada directa a la extensión (DID) (normalmente un número del departamento de seguridad) que debe incluirse en el modo de conferencia cuando se realiza una llamada de emergencia.

<!-- end list -->

  - **Modo de conferencia**  
    Especifica si el URI de conferencia se incluirá en la llamada de emergencia en modo conferencia mediante comunicación unidireccional o bidireccional.

<!-- end list -->

  - **Intervalo de actualización de la ubicación**  
    Especifica la duración (en horas) que transcurre entre las solicitudes de los clientes de una actualización de ubicación desde el Servicio de información de ubicaciones. El valor se puede definir en cualquier número incluido entre 1 y 12. El valor predeterminado es 4.

