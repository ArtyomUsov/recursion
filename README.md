# recursion
Немного рекурсии: коробка которая открывает пока не закончится содержимое.

let box  = {
    items: [
        {name: 'подушка'},
        {name: 'Одеяло'},
        {name: 'сапог'},
        {
            items: [
                {name: 'мотыга'},
                {name: 'лопата'},
                {name: 'нож'},
            ],
            name: 'box',
        },
    ],
    name: 'box',
}


// box.item - число элементов в коробке
// i - индекс
function openBox(box) {
    for (let i = 0; i < box.items.length; i++) {
        let item = box.items[i];
        if (item.name == "box") {
            console.log('вскрываем найденую коробку');
            openBox(item)
        } else {
            console.log(item.name)
        }
    }
}
openBox(box);
