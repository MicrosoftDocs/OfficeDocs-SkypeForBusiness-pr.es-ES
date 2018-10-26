---
title: Requisitos de configuración del proxy inverso de Lync Server 2013
TOCTitle: Requisitos de configuración del proxy inverso de Lync Server 2013
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945651(v=OCS.15)
ms:contentKeyID: 52061736
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de configuración del proxy inverso de Lync Server 2013

 

_**Última modificación del tema:** 2013-03-05_

En Lync Server 2013 es necesario reunir algunos requisitos en las comunicaciones desde el cliente externo que luego pasan a los servicios web externos hospedados en el Director, el Grupo de directores, el Servidor front-end o el Grupo de servidores front-end. El proxy inverso también es responsable de publicar el Servidor Office Web Apps, en caso de estar dando una conferencia a los usuarios.


> [!NOTE]
> Lync Server 2013 no especifica que deba usarse un proxy inverso en concreto. Lync Server 2013 únicamente define los requisitos operativos que el proxy inverso debe ser capaz de cumplir, si bien, por lo general, el proxy inverso que haya implementado en la infraestructura probablemente los reúna.



## Requisitos de proxy inverso

Estas son las operaciones funcionales que Lync Server 2013 espera del proxy inverso:

  - Usar la Capa de sockets seguros (SSL) y la Seguridad de la capa de transporte (TLS) implementadas mediante certificados emitidos por una entidad de certificación pública para conectarse a los servicios web externos publicados del Director, Grupo de directores, Servidor front-end o Grupo de servidores front-end. El Director y el Servidor front-end pueden estar en un grupo de carga equilibrada mediante equilibradores de carga de hardware.

  - Poder publicar sitios web internos mediante certificados para cifrado, o bien publicarlos mediante métodos sin cifrar, en caso necesario.

  - Poder publicar externamente un sitio web hospedado de forma interna usando su nombre de dominio completo (FQDN).

  - Poder publicar todo el contenido del sitio web hospedado. Se puede usar de forma predeterminada la directiva **/\***, que la mayoría de los servidores web identifica como que significa "Publicar todo el contenido en el servidor web". También se puede modificar la directiva, por ejemplo, **/Uwca/\***, que quiere decir "Publicar todo el contenido en el directorio virtual Ucwa".

  - Debe ser configurable para requerir conexiones de Capa de sockets seguros (SSL) o de Seguridad de la capa de transporte (TLS) con los clientes que soliciten contenido de un sitio web publicado.

  - Debe aceptar certificados con entradas de nombre alternativo del firmante (SAN).

  - Debe poder permitir el enlace de un certificado a una interfaz o agente de escucha a través del que el FQDN de servicios web externos vaya a resolverse. Se prefiere una configuración de agente de escucha a una de interfaz. Se pueden configurar varios agentes de escucha en una sola interfaz.

  - Debe permitir la configuración de control de encabezados de host. Con frecuencia, el encabezado de host original enviado por el cliente solicitante debe pasar de forma transparente, en lugar de modificarse a través del proxy inverso.

  - Crear un puente para el tráfico SSL y TLS desde un puerto definido externamente (TCP 443, por ejemplo) a otro puerto definido (TCP 4443, por ejemplo). El proxy inverso puede descifrar el paquete al recibirlo y, seguidamente, volver a cifrarlo en el envío.

  - Crear un puente para el tráfico TCP no cifrado desde un puerto (TCP 80, por ejemplo) a otro (TCP 8080, por ejemplo).

  - Permitir la configuración de los tipos de autenticación NTLM, Sin autenticación y Autenticación de paso a través, o aceptar estos tipos de autenticación.

