# Change log

## Juny 2020
- Afegida operacio consultaAdministracio,
- Modificat element _representacio_ a les consultes de representacions i consulta representacions persona. Per alleugerir el volum de les respostes només s'inclou l'element _evidencies_ a la consultaRepresentacio (consulta d'una representació única).
- Afegit element _origen_ a cada element _evidencia_. D'aquesta manera es pot determinar l'origen que ha provocat la creació d'aquesta evidència.

## Desembre 2019
- Afegida capacitat a representacions Tipus A i B.
- Afegida informació referent a processat de múltiples peticions.
- Afegida informació relativa als camps mínims a informar.

## Novembre 2019
- Actualitzats codis de producte.
- Afegit índex.
- Corregida guia respecte els canvis de l'xsd.
- Refactorització general de la guia.

## Octubre 2019
- Afegida descripció i exemples d'operacions d'Alta i Modificació d'una representació.
- Reestructuració operacions.
- S'elimina l'element _administracioReceptora_ quedant cobert per l'element _solicitant_

## Juliol 2019
- Corregit titol
- Afegit descripció element _tramit_ i detall d'alguns camps de _documentEvidencia_

## Juny 2019
- Afegida explicació dels elements _origen_, _solicitant_, _capacitat_

### ConsultaRepresentacio i ConsultaRepresentacions
- Afegit element _solicitant_
- Afegit element _generaInforme_ i _urlDescarregaInforme_ en la resposta
- Afegit exemple _consultaRepresentacions_ (consulta i  generació d'informe)
- Afegit exemple _consultaRepresentacio_ generació d'informe
- S'elimina el camp _codiAdministracioSolicitantInforme_ ja que queda cobert per l'element _solicitant_
- Corregit exemple ConsultaRepresentacio, afegit _solicitant_
### ValidarRepresentacio
- Es substitueixen els camps _funcionariSolicitant_ i _administracioSolicitant_ per l'element _solicitant_

### Representacio
- Afegit el l'atribut _dataValidacioPoderNotarial_
- Afegit element _solicitant_
- Afeit element _origen_
- Afegit element _idRepresentacioA_

### ValidarRepresentacio
- Corregit exemple validar representació

- Correccions format exemple xml

## Març 2019
- Afegit camp _estat_ per l'element _evidencia_ d'una _representacio_.

## Gener 2019
Càrrega inicial documentació i xsd de la integració al servei Representa a través de la PCI
