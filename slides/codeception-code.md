## Пример реального теста

``` php
public function viewPlan(WebGuy $I)
{    
  // создать начальные данные
  $this->planId = $I->createPlan(['name' => 'plan'.sq(1)]); 
  $I->amOnPage('/plans'); // перейти на страницу
  $I->expect('only one result is matched'); // комментарий
  $I->see('Displaying 1-1 of 1 result.','.summary'); // проверить наличие
  $I->click(PlanPage::$viewButton); // использовать PageObject
  $I->see('plan'.sq(1).' Details', 'h1'); 
}
  ```