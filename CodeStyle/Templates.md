# Templates

- PHP template style
```HTML+PHP
<?php
$items = $this->getAllItems();
$isBlue = $this->checkIfIsBlue();
?><ul class="list<?
    if ($isBlue) :
        ?> blue<?
    endif;
?>"><?
    foreach ($items as $pos => $item) :
        ?><li id="item_<?=$item->getId()?>" class="list-item <?
            if ($item->isSmall()) :
                ?>small<?
            else :
                ?>regular<?
            endif;
        ?>"><?
            echo $item->getName();
            echo $item->getAge();
            ?><a href="<?=$this->url([
                'id' => $item->getId()
            ], 'item-show')?>"><?
                echo $item;
            ?></a>
            <a class="js-action-remove" href="javascript:void(0);" data-action="remove">Remove</a># todo js-action-remove or data-action="remove"
        </li><?
        if ($pos % 4) :
            ?><div class="clear"></div><?
        endif;
    endforeach;
?></ul>
```

- Ruby template style
```Ruby
# todo
```

- EJS template style
```Ruby
# todo
```

- Other
```
# todo
```