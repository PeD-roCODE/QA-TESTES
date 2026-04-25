 TESTE COMPLETO DE AUTOMATIZAÇÃO USANDO SITE DEMOQA.COM
  
Cypress.on('uncaught:exception', (err, runnable) => {
  return false // impede que Cypress falhe com o erro
})

describe('template spec', () => {
  it('passes', () => {
    cy.visit('https://demoqa.com'/) // acessa o site
    cy.get(':nth-child(2) > :nth-child(1) > .card-up').click() // clica na seção de "Elements"
    cy.get(':nth-child(2) > .element-list > .menu-list > #item-0').click() // clica em "text box"
    cy.get('#firstName').type('Jaceta') // preenche o primeiro nome
    cy.get('#lastName').click()
    cy.get('#lastName').type('Costa') // preenche o sobrenome
    cy.get('#userEmail').type('Testee2e2@gmail.com') // preenche o e-mail
    cy.get('#userNumber').type('2195555555')  // preenche o número de telefone
    cy.get('.subjects-auto-completevalue-container').type('Seilaqueporreisso') // digita no campo de matérias (autocomplete)
    cy.get('#currentAddress').type('Rua Mariano Procópio n37') // preenche o endereço
    cy.get('#genterWrapper > .col-md-9 > :nth-child(1) > .custom-control-label').click() // seleciona o gênero "male"
    cy.get('#hobbiesWrapper > .col-md-9 > :nth-child(3) > .custom-control-label').click() // seleciona o hobby "Music"
    cy.get('#dateOfBirthInput').click() // abre o calendário de data de nascimento
    cy.wait(500) // espera meio segundo para garantir que os elementos carregaram
    cy.get('.react-datepickermonth-select').select('July') // seleciona o mês de nascimento
    cy.get('.react-datepickeryear-select').select('2001') // seleciona o ano de nascimento
    cy.get('.react-datepickerday--027:not(.react-datepicker__day--outside-month)').click() // seleciona o dia (27)
    cy.get('#state').click() // abre o menu de estados
    cy.contains('div', 'NCR').click() // clica na opção "NCR"
    cy.get('#city').click() // abre o menu de cidades
    cy.contains('div', 'Delhi').click() // clica na opção "Delhi"
    cy.get('#uploadPicture').attachFile('TONYJAASON.jpg.jfif');

    cy.get('#submit') // Finaliza apertando o botão de envio
  })
}) 
