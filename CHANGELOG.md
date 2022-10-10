# Change log

## Octubre 2022 (A PRE el 20 d'Octubre / A PRO el 26 d'Octubre)
- El camp ja existent tipusDocument de documentEvidencia admetrà a les peticiones només un dels següents 4 valors possibles: SOLICITUD, SOLICITUD_DELEGACIO_SIGNATURA, PODER_NOTARIAL i ALTRES.
  Qualsevol altre valor no serà vàlid i es retornarà el missatge: "El camp tipus de document es incorrecte".

## Setembre 2022
- Afegida nova operació de consulta per recuperar les administracions disponibles al servei (_consultaAdministracions_).
- Afegit nou atribut _dataMaxVigencia_ a l'element _representacio_.
- Afegit nou atribut _idRepresentacioProrroga_.
- Modificat el type de l'element _uuid_ de _tramit_ de xs:string a NonEmptyString.
- Modificat el type de l'element _codiFue_ de _tramit_ de NonEmptyString a xs:string.
- Modificat el type de l'element _uuidFamilia_ de _tramit_ de xs:string a NonEmptyString.

## Març 2022
- Correcció del type d'alguns elements on no estava definit (numRepresentacionsTotal, numPaginesTotal, urlDescarregaInforme).
- Correcció del type de l'element _codiFue_ d'un _tramit_. Un cop informat no es permetia tornar a posar-ho sense cap valor.
- Correcció de la operació _consultarFamilies_. Segons la documentació i la definició del fitxer dadesEspecifiques.xsd anterior, aquesta operació és paginada. Malgrat això, s'ha vist que sempre s'estaven retornant totes les families ja que la paginació en aquesta cerca no és òptima. D'aquesta manera s'eliminen els atributs de la petició _mida_ i _pagina_ i de la resposta els conseqüents _numTotal_ i _numPaginesTotal_.

## Desembre 2021
- Afegit l'element _origen_ dins l'element _solicitant_. 
- Es limita el volum de dades retornades en les consultes de representacions. Fins ara en algunes consultes de representacions es retornava, dins dels elements representacio una llista d'elements evidencia. Per optimitzar les cerques i racionalitzar el pes de les respostes s'elimina aquest atribut (evidencies) d'aquest tipus de respostes. Si es vol recuperar les evidencies d'una representació cal fer-ho consultant una única representació (consultaRepresentacio).
- Afegida descripció capacitat GENERAL.

## Novembre 2021
- Afegida explicació referent a la validació del _valorDocumentIdentificatiu_ de l'element _persona_.
- Corregida la descrpció de l'estat _ANUL·LADA_ i _PENDENT_ACCEPTACIO_.
- Afegida descripció, petició de consulta i resposta de l'element _administracio_.

## Octubre 2021
- Afegit element _tipusPresentador_ a _processarRepresentacio.dades_ i a_evidencia_.
- Valors de l'element _tipusPresentador_: PODERDANT, REPRESENTANT, REPRESENTA, ADMINISTRACIO.
- L'element _validarRepresentacioResponse.response.resultat_ passa a ser _validarRepresentacioResponse.resultat_ (per mantenir coherencia amb la resta de responses on no s'inclou el wrapper _response_).
- Nou estat EN_VALIDACIO.
- Actualitzat el diagrama d'estats.
- Abans hi havia casos en que es retornaven elements del tipus sequence encara que no tinguessin cap element (p. ex. un element familia, quan la seqüència _tramits_ no tenia cap _tramit_ es retornava &lt;familia&gt;...&lt;tramits/&gt;&lt;/familia&gt;. Ara si una familia no te cap tramit no s'inclou cap tag &lt;tramits&gt;.

S'ha activat la validació d'esquema a les respostes (fins ara només es validaven les peticions). Al fer-ho s'ha hagut de modificar alguns atributs i respostes que no s'adecuaven al que l'esquema definia.
- _consultarRepresentacionsResponse_ > _numRepresentacionsTotal_ i _numPaginesTotal_ amb minOccurs=0, ja que si hi ha algun errror no es retornen aquests valors.
- _consultarRepresentacionsPersonaResponse_ > _numTotal_ i _numPaginesTotal_ amb minOccurs=0, ja que si hi ha algun errror no es retornen aquests valors.
- _processarRepresentacioResponse_ > s'afegeix l'atribut minOccurs=0 a l'element _representacio_, ja que quan es produeix algun error no es retorna cap representació.
- _consultarRepresentacionsPersonaRepresentantResponse_ i_consultarRepresentacionsPersonaPoderdantResponse_ > _numPaginesTotal_ i _representacions_ minOccurs=0 ja que si hi ha algun errror no es retornen aquests valors.
- _consultarCatalegResponse_ > atribut minOccurs=0 a l'element _cataleg_, ja que quan es produeix algun error no es retorna cap cataleg.
- _consultarFamiliesResponse_ > _numPaginesTotal_ i _numTotal_ s'afegeix l'atribut minOccurs=0 ja que quan es produeix algun error no es retorna cap familia.
- Afegit minOccurs=0 a l'atribut _administracio_ de l'element _solicitant_.

  
## Març 2021
- Afegit nou estat PENDENT_ACCEPTACIO.
- Corregits exemples validarRepresentacio.

## Gener 2021
- Modificat el tipus de dada _validarRepresentacio_ i _validarRepresentacioResponse_. S'ha afegit l'element _generaEvidencia_ a la petició . Si s'envia a true la resposta inclourà un element _evidenciaSignada_ que conté una signatura en base64 i format XAdES-T_Enveloping que inclou el tag _resultat_ signat.
- S'inclou en la resposta la propia consulta feta (_consultaValidacio_).
- Afegit un nou atribut a l'element _representacio_ anomenat _tipusPresentador_ (opcional) per identificar qui és la persona que presenta la sol·licitud o canvi.


## Juny 2020 (2)
- Afegida operació de _consultaRepresentacionsPersonaPoderdant_.
- Afegida operació de _consultaRepresentacionsPersonaRepresentant_.

_Aquestes operacions retornen els mateixos resultats que _consultaRepresentacionsPersona_ però sense agrupar les representacions segons el rol de poderdant o representant._

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
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTMyNjkxNTM5OCw1MjU0MTUzNTRdfQ==
-->
