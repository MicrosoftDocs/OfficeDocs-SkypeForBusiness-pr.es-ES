---
title: "Lync Server 2013: Instalar sistemas operativos y software necesario para servidores"
TOCTitle: Instalar los sistemas operativos y el software necesario como requisito previo en los servidores
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48274293
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalar los sistemas operativos y el software necesario como requisito previo en los servidores en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Una vez configurado el hardware y la infraestructura del sistema, deberá instalar los sistemas operativos Windows adecuados y sus actualizaciones, además de todo el software necesario como requisito previo en cada uno de los servidores que esté implementando. Esto incluye cada uno de los roles de servidor de Lync Server 2013 y todos los demás servidores de infraestructura adicionales o servidores que ejecuten SQL Server que sean necesarios para la implementación.


> [!NOTE]
> En esta sección se describe la instalación de sistemas operativos y el software necesario como requisito previo para servidores internos. Si está implementando Servidores perimetrales para admitir el acceso de usuarios externos, debe instalar también sistemas operativos y el software necesario como requisito previo para esos servidores, incluidos los Servidores perimetrales y servidores proxy inversos. Para obtener más información acerca de la preparación de servidores para admitir el acceso de usuarios externos, consulte <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparar la instalación de los servidores en la red del perímetro para Lync Server 2013</A> en la documentación referente a la implementación.



## Instalar sistemas operativos Windows en servidores

Instale el sistema operativo Windows adecuado en cada uno de los servidores que va a implementar como se describe a continuación:

  - **Servidores que ejecutan Lync Server 2013**   Para más información acerca de los requisitos del sistema operativo para los servidores que ejecutan Lync Server 2013, vea [Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación de compatibilidad.

  - **Servidores de bases de datos.** Para más información sobre los requisitos del sistema operativo para los servidores de bases de datos, incluida la base de datos back-end, Base de datos de archivado y Base de datos de supervisión, vea la documentación de SQL Server. Para SQL Server 2012, vea los Libros en pantalla de SQL Server 2012 en [http://go.microsoft.com/fwlink/?linkid=218015\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=218015%26clcid=0xc0a).


> [!NOTE]
> Si va a instalar Lync Server 2013 en Windows Server&nbsp;2008&nbsp;R2 con SP1, primero debe instalar la actualización que se describe en el artículo 2646886 de Microsoft Knowledge Base, “SOLUCIÓN: Cuando un módulo llama al método InsertEntityBody en IIS 7.5 se producen daños en el montón” en <A href="http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=3052&amp;clcid=0xC0A</A>.<BR>También debe modificar el registro como se describe en el artículo de Knowledge Base, <A href="http://go.microsoft.com/fwlink/p/?linkid=506893">Los Id. de evento 32402 y 61045 se registran en servidores front-end de Lync Server 2013 que están instalados en Windows Server R2 de 2012</A>.



## Instalar Windows Update en los servidores

Instale las actualizaciones siguientes desde Windows Update en cada servidor:

  - **Windows Update para servidores que ejecutan Lync Server 2013**   Para obtener más información acerca de las actualizaciones de Windows Update requeridas para los servidores que ejecutan Lync Server 2013, consulte [Requisitos adicionales de software para Lync Server 2013](lync-server-2013-additional-software-requirements.md) en la documentación de planeación.

  - **Servidores de bases de datos**   Para obtener información sobre las actualizaciones de Windows Update necesarias para los servidores de bases de datos, incluida la base de datos back-end, Base de datos de archivado y Base de datos de supervisión, vea la documentación de SQL Server 2012. Para SQL Server 2012, vea los Libros en pantalla de SQL Server 2012 en [http://go.microsoft.com/fwlink/?linkid=218015\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=218015%26clcid=0xc0a).

## Instalar otro software necesario como requisito previo en los servidores

Lync Server 2013 requiere la instalación de software adicional siguiente en los servidores:

  - **Software necesario como requisito previo para servidores que ejecutan Lync Server 2013**   El software adicional necesario como requisito previo para los servidores que ejecutan Lync Server 2013 dependerá del rol de servidor que se implemente. Para más información acerca de requisitos de software específicos, vea [Requisitos adicionales de software para Lync Server 2013](lync-server-2013-additional-software-requirements.md) en la documentación sobre planeación.

  - **Windows Identity Foundation.**Lync Server 2013 requiere la instalación de Windows Identity Foundation para admitir los escenarios de autenticación de servidor a servidor. Para comprobar si se ha instalado en el equipo, vaya a Panel de control, haga clic en **Programas y características**, **Ver actualizaciones instaladas** y mire en **Microsoft Windows**. Para obtener información sobre la instalación de Windows Identity Foundation, vea [http://go.microsoft.com/fwlink/?linkid=204657\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=204657%26clcid=0xc0a).

  - **Microsoft .NET Framework 4.5**   Necesitará la versión de 64 bits de Microsoft .NET Framework 4.5 para Lync Server 2013.

  - **Software necesario como requisito previo para servidores de bases de datos** Para obtener información sobre el Windows Update necesario para servidores de bases de datos, incluida la base de datos back-end, Base de datos de archivado y Base de datos de supervisión, vea la documentación de SQL Server 2012 en [http://go.microsoft.com/fwlink/?linkid=218015\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=218015%26clcid=0xc0a).
    

    > [!NOTE]
    > Lync Server 2013 instala automáticamente Microsoft SQL Server 2012 Express en cada Servidor Standard Edition y en cada servidor que ejecuta Lync Server 2013 en el que se ubica el almacén de configuración local.



  - **Tiempo de ejecución de Windows Media Format**   Todos los Servidores front-end y Servidores Standard Edition en los que se vayan a implementar las conferencias deben tener instalado el Tiempo de ejecución de Windows Media. El Tiempo de ejecución de Windows Media Format es necesario para ejecutar los archivos de audio de Windows Media (.wma) que reproducen las aplicaciones de estacionamiento de llamadas, anuncio y grupo de respuesta para los anuncios y la música.
    

    > [!NOTE]
    > Para Windows Server 2012 y Windows Server 2012 R2, el Tiempo de ejecución de Windows Media Format se instala con Microsoft Media Foundation.

    

    > [!NOTE]
    > Para Windows Server&nbsp;2008 y Windows Server&nbsp;2008&nbsp;R2, el Tiempo de ejecución de Windows Media Format se instala como parte de la experiencia de escritorio de Windows. Se recomienda instalar la experiencia de escritorio de Windows antes de instalar Lync Server 2013. Si Lync Server 2013 no encuentra este software en el servidor, le solicitará que lo instale y, a continuación, deberá reiniciar el servidor para completar la instalación.


