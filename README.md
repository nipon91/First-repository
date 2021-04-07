import wixData from 'wix-data';

$w.onReady(function () {
});

export async function sortBy_change(event) {
	defaultSort = await false;
	  if($w("#sortBy").value === 'Price High to Low') {
		$w("#dynamicDataset").setSort(wixData.sort()
		.descending("price")
		);
	} else if($w("#sortBy").value === 'Price Low to High') {
		$w("#dynamicDataset").setSort(wixData.sort()
		.ascending("price")
		);
	}
}

let defaultSort = false;

export async function reset_click(event) {
	$w("#sortBy").value = await undefined;
	defaultSort = await true;
}
