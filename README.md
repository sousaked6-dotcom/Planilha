=SEERRO(
 LET(
  dados;
   QUERY(
    IMPORTRANGE("https://docs.google.com/spreadsheets/d/1a-3YiuVzWagmmRNB2PesJuz3SUKs0jj9L2KNNQoXn5U/edit";
                "dados1!A:AN");
    "SELECT Col27, Col34, Col37 WHERE Col1 = "&VALOR(A1);
    0
   );
  facility; ÍNDICE(dados;1;1);
  ciclo; ÍNDICE(dados;1;2);
  dataeta; ÍNDICE(dados;1;3);
  SE(
   facility<>"SSP21";
   "CASO PS";
   SE(
    OU(ciclo="";dataeta="");
    "CASO PS";
    "PROMESSA"
   )
  )
 );
 "ID NÃO ENCONTRADO"
)
