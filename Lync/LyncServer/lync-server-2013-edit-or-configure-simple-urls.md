---
title: 'Lync Server 2013: Editar o configurar direcciones URL sencillas'
TOCTitle: 'Editar o configurar direcciones URL sencillas '
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48274224
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Editar o configurar direcciones URL sencillas en Lync Server 2013

 

_**Última modificación del tema:** 2014-02-04_

Este procedimiento no requiere pertenencia al grupo de dominio con privilegios o de administrador local. Deberá iniciar sesión en un equipo como usuario estándar.

Lync Server 2013 usa direcciones URL simples para dirigir las llamadas internas y externas a servicios que están en el Servidor front-end o en el Director (si hay uno implementado). Para más información sobre las direcciones URL simples, vea [Planeación de las direcciones URL simples en Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) en la documentación de planeación. Existen varias opciones de formato para las URL simples. Para más información sobre estas opciones, vea [Requisitos de DNS para direcciones URL simples en Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) en la documentación de planeación.

De forma predeterminada, las direcciones URL sencillas se configurarán con el formato (por ejemplo, la dirección URL sencilla de acceso telefónico): https://dialin.\<SIP domain\>

## Para configurar direcciones URL sencillas

1.  En Generador de topologías, haga clic con el botón secundario en el nodo **Lync Server** y luego haga clic en **Editar propiedades**.

2.  En el panel **Direcciones URL simples**, seleccione **Direcciones URL de acceso telefónico:** (Acceso telefónico) o **Direcciones URL de reunión:** (Reunión) para editarlas. Después, haga clic en **Editar dirección URL**.

3.  Actualice la dirección URL con el valor que desee y, a continuación, haga clic en **Aceptar** para guardar la dirección URL modificada. En el ejemplo que se muestra aquí, se ha cambiado la dirección URL de marcado por https://pool01.contoso.net/dialin.

4.  Edite la dirección URL de reunión realizando los mismos pasos, si es necesario.

## Para definir la dirección URL sencilla de administración opcional

1.  En Generador de topologías, haga clic con el botón secundario en el nodo **Lync Server** y luego haga clic en **Editar propiedades**.

2.  En el cuadro **Dirección URL de acceso administrativo**, escriba la dirección URL sencilla que desee para configurar el acceso administrativo a Panel de control de Lync Server 2013 y, a continuación, haga clic en **Aceptar**.
    
    > [!TIP]  
    > Le recomendamos que use la dirección URL más sencilla que sea posible para la dirección URL de administración. La opción más sencilla es <strong>https://admin</strong> <em>&lt;domain&gt;</em> .
    
    
    > [!IMPORTANT]  
    > Si cambia una dirección URL simple tras la implementación inicial, debe saber qué cambios afectan a los certificados y los registros de su sistema de nombres de dominio (DNS) para direcciones URL simples. Si el cambio afecta a la base de una dirección URL simple, debe cambiar también los certificados y registros DNS. Por ejemplo, si se cambia https://lync.contoso.com/Meet por https://meet.contoso.com, se cambia la dirección URL básica lync.contoso.com por meet.contoso.com, por lo que debe modificar los certificados y registros DNS para que hagan referencia a meet.contoso.com. Si cambia la dirección URL simple https://lync.contoso.com/Meet por https://lync.contoso.com/Meetings, la dirección URL básica lync.contoso.com no cambia, por lo que no será necesario cambiar el certificado ni el DNS. Sin embargo, cuando cambie el nombre de una dirección URL simple, deberá ejecutar el cmdlet <strong>Enable-CsComputer</strong> en cada Director y Servidor front-end para registrar el cambio.
    


## Vea también

#### Conceptos

[Planeación de las direcciones URL simples en Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

