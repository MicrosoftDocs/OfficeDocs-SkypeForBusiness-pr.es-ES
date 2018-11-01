---
title: 'Lync Server 2013: Plan para certificados de servidores perimetrales'
TOCTitle: Plan para certificados de servidores perimetrales
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48277143
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Plan para certificados de servidores perimetrales en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-05_

La creación de certificados para servidores perimetrales se simplifica en Lync Server 2013.

**Diagrama de flujo de certificados para servidor perimetral**

![Diagrama de flujo de certificados](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "Diagrama de flujo de certificados")

Cree un certificado público único, compruebe que tiene una clave privada exportable definida para el certificado y asígnela a las interfaces externas del servidor perimetral usando el asistente para certificados:

> [!IMPORTANT]  
> Lync Server no admite certificados de comodín, salvo cuando se usan para resumir las direcciones URL simples a través de proxy inverso. Se deben definir nombres alternativos del firmante (SAN) por cada nombre de dominio SIP, Servicio perimetral de conferencia web, Servicio perimetral A/V y dominio XMPP que la implementación ofrezca.




> [!NOTE]
> A partir de Lync Server 2013, los certificados de autenticación de audio y vídeo de ensayo antes de la fecha de expiración del certificado actual requieren cierta planeación adicional. En lugar de un certificado con diversos fines para la interfaz externa del servidor perimetral, necesitará dos certificados, uno asignado al Servidor perimetral de acceso y al Servicio perimetral de conferencia web y otro, al certificado para el Servicio perimetral A/V. Si desea más información, consulte <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate">Prueba de certificados de OAuth y audio y vídeo en Lync Server 2013 utilizando -Roll en Set-CsCertificate</A>



> [!IMPORTANT]  
> En el caso de un grupo de Servidores perimetrales, el certificado se exporta con la clave privada de cada Servidor perimetral y se asigna el certificado a cada servicio Servidor perimetral. Haga lo mismo para el certificado interno de Servidor perimetral, exportar el certificado con la clave privada y asígnelo a cada interfaz interna del servidor perimetral.



  - Compruebe que se ha asignado la clave privada exportable al certificado

  - Servidor perimetral de acceso (denominado **Servidor perimetral externo de acceso SIP** en el asistente para certificados)

  - Servicio perimetral de conferencia web (denominado **Servidor perimetral externo de conferencia web** en el asistente para certificados)

  - Servicio de autenticación A/V (denominado **Servidor perimetral externo de A/V** en el asistente para certificados)

Cree un solo certificado interno con una clave privada exportable, cópielo y asígnelo a cada una de las siguientes interfaces internas de servidor perimetral:

  - Servidor perimetral (denominado **Servidor perimetral interno** en el asistente para certificados)

> [!IMPORTANT]  
> Se pueden utilizar otros certificados independientes y distintivos para cada servicio de Servidor perimetral. Un buen motivo para seleccionar certificados aparte es que se desee utilizar la nueva característica de implementación de certificados para el certificado Servicio perimetral A/V. En el caso de esta característica, se recomienda disociar el certificado Servicio perimetral A/V de Servidor perimetral de acceso y Servicio perimetral de conferencia web. Si decide solicitar, adquirir y asignar certificados aparte para cada servicio, deberá solicitar que la clave privada sea exportable para el Servicio perimetral A/V (una vez más, es en realidad el servicio de autenticación A/V) y asignar el mismo certificado a la interfaz interna de perimetral A/V en cada Servidor perimetral.



## Vea también

#### Tareas

[Prueba de certificados de OAuth y audio y vídeo en Lync Server 2013 utilizando -Roll en Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)  

#### Conceptos

[Cambios en Lync Server 2013 que afectan a la planificación del servidor perimetral](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

